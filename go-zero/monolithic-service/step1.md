# Prepare

## 准备工作
1.安装 goctl

` GO111MODULE=on GOPROXY=https://goproxy.cn/,direct go get -u github.com/tal-tech/go-zero/tools/goctl`{{execute}}

2.验证 goctl

`goctl --version`{{execute}}

## 创建工程
1.创建 go-zero-demo 目录

```
export WORK_DIR="$pwd/go-zero-demo"
mkdir -p $WORK_DIR && cd $WORK_DIR
```{{execute}}

2.go mod 初始化

`go mod init go-zero-demo`{{execute}}

## 创建服务
1.生成 greet 服务

`goctl api new greet`{{execute}}

2. go mod tidy

`go mod tidy`{{execute}}

3.查看 greet 目录结构

```
cd $WORK_DIR/greet && tree
```{{execute}}

## 修改代码逻辑

复制如下代码至 `/go-zero-demo/greet/internal/logic/greetlogic.go`{{open}} 的第 28 行

```
resp=&types.Response{
    Message: "Hello go-zero",
}
```{{copy}}

## 运行示例
`go run greet.go`{{execute}}

## 验证结果

访问接口 `curl -i -X GET http://localhost:8888/from/you`{{execute T2}}