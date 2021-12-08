---
id: 869dd24f-104c-4936-b735-06f09d0566f9
title: r.node.files.zip
desc: ''
updated: 1
created: 1

customLegacy:
  path: r.node.files.zip
---


```ts
import fs from 'fs';
import archiver from 'archiver';

function setupArchiver({onClose, onErr, out}) {
  const output = fs.createWriteStream(out);
  const archive = archiver('zip', {
    zlib: { level: 9 } // Sets the compression level.
  });

  output.on('close', function() {
    console.log(archive.pointer() + ' total bytes');
    console.log('archiver has been finalized and the output file descriptor has closed.');
    onClose()
  });
  output.on('end', function() {
    console.log('Data has been drained');
  });
  archive.on('warning', function(err) {
    console.log({err});
    onErr(err)
  });
  archive.on('error', function(err) {
    console.log({err});
    onErr(err)
  });
  archive.pipe(output);
  return {
    archive
  }
}

export function zipDir({dirPath, out}): Promise<{
  out: string // path to file
  status: 'ok'|'empty'
}>{
  return new Promise( (resolve, reject) => {
    const {archive} = setupArchiver({out, onClose: () => {
      resolve({out, status: 'ok'})
    },
      onErr: (err) => {
        reject(err)
      }
    })

    fs.readdir(dirPath, function(err, files) {
      if (err) {
        // TODO
      } else {
        if (!files.length) {
          resolve({out, status: 'empty'})
        }
      }
    })

    archive.directory(dirPath, '.')
    archive.finalize()
  })
}

```
