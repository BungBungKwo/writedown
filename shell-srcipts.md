# Shell 脚本（Shell Scripting）

> 特点及优势：
> - 方便复用
> - 减少复用时重写错误
> - 多工具组合
> - 无需编译

**常见shell**

sh, csh, tcsh, ksh, bash

**注释**

```
# Comment
```

**命令解释器指定**

```
#!/path/to/CommandInterpreter
```

**命令串接（Chaining Commands）**

命令串接方式：
- `;`：无论前命令是否成功执行，后命令定然可执行
- `&&`：后续命令受前命令影响
- `||`：逐一执行直到命令成功

对比pipe，pipe在后续命令开始前退出当前命令
