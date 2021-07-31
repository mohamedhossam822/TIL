Assume we have **sympotms_disease.py** file, we need to send some data to this file and we expect it to return some data as well<br>
We run the following
```javascript
const util = require('util');
const execFile = util.promisify(require('child_process').execFile);
const symptomModel = async (symptoms) => {
  const {stdout} = await execFile('python', ['controllers/FunctionalModels/sympotms_disease.py', symptoms]);
  return stdout
};
```
The python file reads the data as **symptoms** and return the result as **stdout**

sympotms_disease.py
```python
import sys
arg = sys.argv[1]
print("Return value : ",func(arg))
```

* [Child process docs](https://nodejs.org/api/child_process.html#child_process_child_process_execfile_file_args_options_callback)
