# utils

// 社会统一信用代码 长度18位 由大写字母和数字组成 不包含大写字母(I、O、Z、S、V),前2位和后10位由数字或字母组成中间6位由数字组成

function verifyCUSCC(cuscc) {
  var cusccReg = /^[0-9A-HJ-NPQRTUWXY]{2}\d{6}[0-9A-HJ-NPQRTUWXY]{10}$/;
  if(!cusccReg.test(cuscc)){
      return false;
  } else {
      return true;
  }
}

// 纬度正则 整数部分为0-90小数部分为0到6位

function verifylatitude(latitude) {
  var latreg = /^(\-|\+)?([0-8]?\d{1}\.\d{0,6}|90\.0{0,6}|[0-8]?\d{1}|90)$/;
  if(!latreg.test(latitude)){
      return false;
  } else {
      return true;
  }
}

// 经度正则 整数部分为0-180小数部分为0到6位

function verifylongitude(longitude) {
  var longreg = /^(\-|\+)?(((\d|[1-9]\d|1[0-7]\d|0{1,3})\.\d{0,6})|(\d|[1-9]\d|1[0-7]\d|0{1,3})|180\.0{0,6}|180)$/;
  if(!longreg.test(longitude)){
      return false;
  }else {
      return true;
  }
}
// undefined || null
export function isNone(object) {
  if (object === undefined || object === null) {
    return true
  }
  return false
}

// 判断对象类型
export function checkObjType(object, type) {
  if (!isNone(object) && object.constructor === type) {
    return true
  }
  return false
}

// 空数组
export function isArrayEmpty(array) {
  if (checkObjType(array, Array) && array.length > 0) {
    return false
  }
  return true
}

// 空字符串
export function isTextEmpty(text) {
  if (checkObjType(text, String) && text !== '') {
    return false
  }
  return true
}
