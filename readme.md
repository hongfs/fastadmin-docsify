# Fastadmin 生成 Docsify 文档工具

## 使用

安装依赖：

```shell
$ composer require hongfs/fastadmin-docsify:dev-main -vvv
```

引入命令：

`application/command.php`

```php
return [
    ...
    'Hongfs\FastadminDocsify\Generate',
];
```

生成：

```shell
$ php think docsify --force=true
```

## 示例

```php
/**
 * 测试方法
 *
 * @ApiTitle    (测试名称)
 * @ApiSummary  (测试描述信息)
 * @ApiMethod   (POST)
 * @ApiBody 	(更多信息内容)
 * @ApiRoute    (/api/demo/test/id/{id}/name/{name})
 * @ApiHeaders  (name=token, type=string, required=true, description="请求的Token")
 * @ApiParams   (name="id", type="integer", required=false, description="会员ID")
 * @ApiParams   (name="name", type="string", required=true, description="用户名")
 * @ApiParams   (name="data", type="object", sample="{'user_id':'int','user_name':'string','profile':{'email':'string','age':'integer'}}", description="扩展数据")
 * @ApiReturnParams   (name="code", type="integer", required=true, sample="0")
 * @ApiReturnParams   (name="msg", type="string", required=true, sample="返回成功")
 * @ApiReturnParams   (name="data", type="object", sample="{'user_id':'int','user_name':'string','profile':{'email':'string','age':'integer'}}", description="扩展数据返回")
 * @ApiReturn   ({"code":"1","msg":"返回成功","more":"这里记得要能被格式化的格式"})
 */
public function test()
{
    $this->success('返回成功', $this->request->param());
}
```

## License

MIT
