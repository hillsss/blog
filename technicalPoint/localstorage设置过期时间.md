```js
// 设置LocalStorage过期时间
Storage.prototype.setExpire = (key, value, expire) => {
  const todayYear = new Date().getFullYear()
  const todayMonth = new Date().getMonth()
  const todayDay = new Date().getDate()
  const todayTime = new Date(todayYear, todayMonth, todayDay, '23', '59', '59').getTime()
  const obj = {
    data: value,
    time: todayTime,
    expire
  }
  // localStorage 设置的值不能为对象,转为json字符串
  localStorage.setItem(key, JSON.stringify(obj))
}

Storage.prototype.getExpire = (key) => {
  let val = localStorage.getItem(key)
  if (!val) {
    return val
  }
  val = JSON.parse(val)
  // console.log(Date.now() - val.time)
  if (Date.now() - val.time >= val.expire) {
    localStorage.removeItem(key)
    return null
  }
  return val.data
}
```