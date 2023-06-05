# Get all files in folder and subfolders recursively

**Tags:** `nodejs, filesystem, recursive`


```javascript
const fs = require('fs');

let files = [];
function GetFilesInFolderRecursive(folder) {
  fs.readdirSync(folder).forEach(file => {
      const fullpath = path.join(folder, file);
      if (fs.statSync(fullpath).isDirectory()) {
        return GetFilesInFolderRecursive(fullpath)
      } else {
        return files.push(fullpath);
      }
  });
}
```
