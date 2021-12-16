---
id: 1bbdd612-e88c-42d3-a6bf-0dceecd293fb
title: Fetch
desc: ''
updated: 1606613231283
created: 1606613131154
---


# Cook

### post request
```js
function createGist(opts) {
  ChromeSamples.log('Posting request to GitHub API...');
  fetch('https://api.github.com/gists', {
    method: 'post',
    body: JSON.stringify(opts)
  }).then(function(response) {
    return response.json();
  }).then(function(data) {
    ChromeSamples.log('Created Gist:', data.html_url);
  });
}

function submitGist() {
  var content = document.querySelector('textarea').value;
  if (content) {
    createGist({
      description: 'Fetch API Post example',
      public: true,
      files: {
        'test.js': {
          content: content
        }
      }
    });
  } else {
    ChromeSamples.log('Please enter in content to POST to a new Gist.');
  }
}

var submitBtn = document.querySelector('button');
submitBtn.addEventListener('click', submitGist);

```