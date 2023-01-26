{foreach name="docsList" id="docs"}

# {$key}

{foreach name="docs" id="api" }


## {$api.title}

{if condition="$api.summary !== $api.title"}


> {$api.summary}
{/if}

{if condition="$api.body"}


{$api.body}
{/if}


**请求方式：**
- {$api.method|strtoupper}


**请求URL：**
- ` {$api.route} `
{if condition="count($api.headersList)"}

**请求头：**

| 参数 | 类型 | 必填 | 描述 | 示例 |
| -----| ---- | ---- | ---- | ---- |
{foreach name="api.headersList" id="param" }
| {$param.name} | {$param.type} | {$param.required ? '是' : '否'} | {$param.description} | {$param.sample} |
{/foreach}
{/if}
{if condition="count($api.paramsList)"}

**请求参数：**

| 参数 | 类型 | 必填 | 描述 | 示例 |
| -----| ---- | ---- | ---- | ---- |
{foreach name="api.paramsList" id="param" }
| {$param.name} | {$param.type} | {$param.required ? '是' : '否'} | {$param.description} | {$param.sample} |
{/foreach}
{/if}
{if condition="count($api.returnHeadersList)"}

**返回头：**

| 参数 | 类型 | 必填 | 描述 | 示例 |
| -----| ---- | ---- | ---- | ---- |
{foreach name="api.returnHeadersList" id="param" }
| {$param.name} | {$param.type} | {$param.required === 'Yes' ? '是' : '否'} | {$param.description} | {$param.sample} |
{/foreach}
{/if}
{if condition="$api.return"}
{if condition="count($api.returnParamsList)"}

**返回参数：**

| 参数 | 类型 | 描述 | 示例 |
| -----| ---- | ---- | ---- |
{foreach name="api.returnParamsList" id="param" }
| {$param.name} | {$param.type} | {$param.description} | {$param.sample} |
{/foreach}
{/if}
{if condition="$api.return"}

**返回数据：**

```json
{$api.return}

```
{/if}
{/if}
{/foreach}{/foreach}

----

> Generated on {:date('Y-m-d H:i:s')} - Powered by [fastadmin-docsify](https://github.com/hongfs/fastadmin-docsify)
