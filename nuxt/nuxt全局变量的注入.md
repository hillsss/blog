# nuxt全局变量引入

1.首先下载@nuxtjs/style-resources

+ yarn add @nuxtjs/style-resources -D

2.之后在nuxt.config.js里添加

```
//.......
 modules: [
  '@nuxtjs/style-resources'
 ],
 styleResources: {
  sass: [],
  scss: ['./assets/scss/*.scss'],
  less: [],
  stylus: []
 }
//.......
```


3.引入多个文件可以把路径改为./assets/scss/*.scss，把你想要全局注入的文件放在scss目录下就行了

4.**注意：定义变量后面要加`;` 否则会报错**
```
$themeColor:red;
```