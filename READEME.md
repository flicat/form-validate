表单验证手机版
-------

调用方法：


- `from.isCheck([tip])`  检查表单是否通过验证[boolean]，参数tip： 是否显示提示信息
- `form.bindCheck([event])` 绑定即时验证，参数 event：可选，默认触发事件为 change
- `form.validateTip(elem, rule, tip)` 可选配置，验证提示信息回调函数。默认在表单元素后添加 提示
  参数 elem：当前验证的节点；rule：验证规则，成功则为 'succeed'；tip：默认验证提示信息。

需要验证的表单元素需要添加属性 `data-validate`，以下元素不在验证范围内：`['submit', 'reset', 'button', 'hidden', undefined]`

data-validate 属性格式：

- 验证单一格式：`data-validate="empty"`
- 验证多个格式：`data-validate="empty,email"`
- 验证是否符合其中一个：`data-validate="phone|email"`
- 多个规则组合验证： `data-validate="empty,phone|email"`

data-validate 属性值：

- `empty`：验证非空
- `email`：验证电子邮件
- `phone`：验证手机号码
- `tell`：验证固话
- `number`：验证数字
- `integer`：验证整数
- `url`：验证网址
- `password`：验证密码
- `cn`：验证中文
- `plus`：验证正整数
- `checkval`：验证值是否与其他表单元素相同，
             使用方法： `checkval([selector])` selector为表单元素选择器
             例如 `data-validate="checkval([name='password'])"`
