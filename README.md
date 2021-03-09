# wasm-golang
hello world with Wasm+go+tinygo


Prerequisite:

1)Install go and setup go environment.
2)Install tinygo

Steps:
1)Create a workspace inside go/src directory.
2)git clone https://github.com/niranjan1825/wasm-golang.git
3)Build without tinygo --> GOOS=js GOARCH=wasm go build -o main.wasm  OR
Build with tinygo ---> tinygo build -o main.wasm -target wasm ./main.go  ( might throw error as some go libraries not supported by tinygo)
4) go run main.go (It will listen on port 8080)


# wasm_exec.js file can be copied from go env GOROOT with command: 
cp "$(go env GOROOT)/misc/wasm/wasm_exec.js" .

# build with tinygo compresses the binary file to 258KB while compiled binary file withoout tinygo was of 2.4MB.(might be diff)


# Some Go libraries not supported by tinygo.So you might get error while compiling the main.go with tinygo.Please refer below link for more details:
https://tinygo.org/lang-support/stdlib/