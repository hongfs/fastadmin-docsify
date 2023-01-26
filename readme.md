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

## License

MIT
