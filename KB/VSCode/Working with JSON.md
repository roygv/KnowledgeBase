
# Overview
You can edit JSON files and validate them against their JSON schema without installing any extension. Simply insert a $schema tag with a value pointing to a JSON schema.
If you are editing a JSON schema, point to: "http://json-schema.org/draft-07/schema"
You can watch a demonstration in this short [video](https://youtu.be/m30JiCuW42U)
To kick off Intellisense type ```<ctrl><space>```
If you got an error in a schema with the location of the error specified as an offset in characters into the file, use the following workaround to get there:
Place the cursor in the begining of the file. Use  ```<shift><click>```  to select a range and look at the number of characters selected as shown in the status bar next to "Ln #, Col #".

# JSON Schema validator in python
https://github.com/python-jsonschema/jsonschema



