# 第二章

## 这是第二章节的内容

```javascript
function isObject(obj){
  var type = typeof obj;
  return type === 'function' || type === 'object' && !!obj;
}

function isArray(obj){
  return Object.prototype.toString.call(obj) === '[object Array]';
}

function allKeys(obj){
  if(!isObject(obj)) return [];
  var _keys = [];
  for(var key in obj) _keys.push(key);
  return _keys;
}

function extend(obj){
  var length = arguments.length;
  if(length < 2 || obj == null) return obj;
  for(var index = 1; index < length; index++){
    var source = arguments[index];
    var _keys = allKeys(source);
    var length = _keys.length;
    for(var i = 0; i < length; i++){
      var key = _keys[i];
      if(obj[key] === void 0) obj[key] = source[key];
    }
  }
  return obj;
}

function clone(obj){
	if(!isObject(obj)) return obj;
  return isArray(obj) ? obj.slice() : extend({}, obj);
}

```

