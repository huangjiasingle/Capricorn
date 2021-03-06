## 打包和工具链

- 如何组织Go代码
- 使用Go语言自带的命令
- 使用其他开发者提供的工具
- 与其他开发者合作

### 包

- 所有的.go文件，除了空行和注释，都应该在第一行声明自己所属的包
- 每个包都在一个单独的目录里
- 不能把多个包放到同一个目录中，也不能把同一个包的文件分拆到多个不同目录中
- 同一个目录下的所有.go文件必须声明同一个包名

#### 包名惯例

- 给包命名的惯例是使用包所在目录的名字
- 给包及其目录命名时，应该使用简洁、清晰且全小写的名字，这有利于开发时频繁输入包名
- 并不需要所有包的名字都与别的包不同，因为导入包时是使用全路径的，所以可以区分同名的不同包
- 一般情况下，包被导入后会使用你的包名作为默认的名字，不过这个导入后的名字可以修改、

#### main包

- 所有用Go语言编译的可执行程序都必须有一个名叫main的包
- 当编译器发现某个包的名字为main时，它一定也会发现名为main()的函数，否则不会创建可执行文件
- main()函数是程序的入口，所以，如果没有这个函数，程序就没有办法开始执行

### 导入
[import导入包语法介绍](./import导入包语法介绍.md)

### 函数 `init`
- 每个包可以包含任意多个 `init` 函数，这些函数都会在程序执行开始的时候被调用。
- 所有被编译器发现的 `init` 函数都会安排在 `main` 函数之前执行。
- `init` 函数用在设置包、初始化变量 或者其他要在程序运行前优先完成的引导工作。

### `Go` 开发工具
[Go语言命令行操作命令](./Go语言命令行操作命令.md)

### 与其他 `Go` 开发者合作

- 包应该在代码库的根目录中
- 包可以非常小
- 对代码执行 `go fmt`
- 给代码写文档

### 依赖管理

#### dep
[dep](https://github.com/golang/dep)
[Dependency management for Go](https://golang.github.io/dep/)

#### gb
[gb](https://github.com/constabulary/gb/)
[A project based build tool for the Go programming language.](https://getgb.io/)


### 小结

- 在 Go 语言中包是组织代码的基本单位。
- 环境变量 GOPATH 决定了 Go 源代码在磁盘上被保存、编译和安装的位置。
- 可以为每个工程设置不同的 GOPATH，以保持源代码和依赖的隔离。
- go 工具是在命令行上工作的最好工具。
- 开发人员可以使用go get来获取别人的包并将其安装到自己的GOPATH指定的目录。
- 想要为别人创建包很简单，只要把源代码放到公用代码库，并遵守一些简单规则就可以了。
- Go 语言在设计时将分享代码作为语言的核心特性和驱动力。
- 推荐使用依赖管理工具来管理依赖。