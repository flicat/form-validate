表单验证手机版
-------

**调用方法**：

- `fromElement.isCheck([tip])`  
检查表单是否通过验证[boolean]，参数tip：可选，是否显示提示信息，默认false。
例如：`document.querySelector('form').isCheck(true);`

- `fromElement.bindCheck([event])` 
绑定即时验证，参数 event：可选，默认触发事件为 `change`
例如：`document.querySelector('form').bindCheck('blur');`

**data-validate**

需要验证的表单元素需要添加属性 `data-validate`
以下元素不在验证范围内：`['submit', 'reset', 'button', 'hidden', undefined]`
例如：`<input type="text" data-validate="empty,email"/>`

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
             使用方法： `checkval([selector])`  参数 selector：表单元素选择器
             例如： `data-validate="empty,checkval([name='password'])"`
- `len：验证值的长度
             使用方法： `len([number])`
             例如 `data-validate="len(11)"`
- `minlen：验证值的最小长度
             使用方法： `minlen([number])`
             例如 `data-validate="minlen(1)"`
- `maxlen：验证值的最大长度
             使用方法： `maxlen([number])`
             例如 `data-validate="maxlen(20)"`
