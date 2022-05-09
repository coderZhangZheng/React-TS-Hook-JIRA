# React-TS-Hook-JIRA

npx create-react-app jira --template typescript
tsconfig.json
        "baseUrl":"./src"
yarn add --dev --exact prettier //团队成员格式化工具,查看 prettier 官网
echo {} > .prettierrc.json      //新建文件，echo表示写入
echo {} > .prettierignore
yarn prettier --write .         //这是手动格式化命令,但项目中需要配置自动格式化(保存前自动格式化)
npx mrm lint-staged             //执行后,会在package.json中有相应配置
yarn add eslint-config-prettier -D   //cra脚手架自带eslint，因为eslint和prettier一起使用有冲突，所以需要安装该npm包来兼容
                                      同时修改package.json中eslintConfig配置，在最下面添加prettier，意思是使用prettier规则覆盖上面的规则
npm install --save-dev @commitlint/{config-conventional,cli}     //下面两个命令作用是规范git commit的书写规范，不符合规范则git提交失败
echo "module.exports = { extends: ["@commitlint/config-conventional"] }" > commitlint.config.js
yarn add json-server -D
echo {} > db.json   //再写入一些数据
json-server --watch db.json   

————————————————————————————————————————————————————————
常见的MOCK方案
1.代码侵入(项目代码中写死数据)-极力不推荐
2.Mock.js-功能有限-只能模拟假数据-无法增删改
3.请求拦截-通过接口管理工具-rap,swagger,yapi等-缺点是依赖后端，配置麻烦
4.安装本地node服务器-配置方便使用简单-（json-server）
————————————————————————————————————————————————————————
REST API
GET     查看(列表，详情)
POST    增加
PUT     替换-全量替换
PATCH   修改
DELETE  删除
————————————————————————————————————————————————————————
decodeURIComponent("%E9%AA%91%E6%89%8B%E7%AE%A1%E7%90%86")?是什么？使用场景？encodeURIComponent("骑手管理")
总结: btoa,atob————编码解码二进制或ASCII字符，如果编译有unicode字符则会报错
      decodeURIComponent,encodeURIComponent————编码解码Unicode字符,无论编码什么字符都不会报错，最多有些字符不编码
      decodeURI,encodeURI————编码解码使用范围小一些
