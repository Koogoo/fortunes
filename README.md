## 词库下载
```bash
git clone https://github.com/Koogoo/fortunes.git
```

## 词库来源:
```bash
https://github.com/ruanyf/fortunes
```

## 截图
![](./screenshot.png)

## 命令
```bash
$ fortune [OPTIONS] [/path/to/fortunes]
```

选项
```
-c     显示词库所在的文件
-f     显示文件库占用比例详情
-e     使文件库显示的机率相等
```

例子: `-c`

```bash
$ fortune -c

(chinese)
%
岭上晴云披絮帽，树头初日挂铜钲
        -  民谚

```

例子: `-f`

```bash
$ fortune -f

100.00% /usr/share/games/fortunes
     0.03% ascii-art
    98.42% chinese
     0.36% song100
     1.19% tang300
```

例子:  `-e`

```bash
$ fortune -e chinese fortunes
#  相当于
$ fortune 50% chinese 50% fortunes

$ fortune -e chinese fortunes tang300 song100
#  相当于
$ fortune 25% chinese 25% fortunes 25% tang300  25% song100
```

## 可以根据自己的喜好,选择要显示的词库
根据自己的喜好,将命令和词库写到 `~/.bashrc` 或 `~/.zshrc` 文件中
```bash
alias fortune-ch='fortune 55% tang300 25% song100 5% ascii-art chinese'
#自定义tang300,song100,ascii-art词库显示机率,省下的显示机率由chinese词库补齐
```

# 添加自己的词库数据

(1) 将词库保存到文件

(2) 每个词库后边添加一行百分号的行(%)

#### 例如:
```
天若有情天亦老，不如与天竞自由
	-  摘自 吴佳明·《逍遥游》
%
“只要有人地方，就有恩怨，有恩怨地方，就有江湖，人就是江湖。”
	-  佚名
%
```

(3) 生成索引文件

```bash
strfile -c % your-fortune-file your-fortune-file.dat
```

(4) 将词库文件及其索引文件移动到 `/usr/share/games/fortunes/`