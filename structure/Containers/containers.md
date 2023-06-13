Refrence:[Containers From Scratch • Liz Rice • GOTO 2018 - YouTube](https://www.youtube.com/watch?v=8fi7uSYlOdc&t=35s)

### Namespaces
- Namespaces are whta u can see,some things process can see 
- When u run  a container under docker,might be 
```Go
// run <image> <cmd> <params>
func main(){
	switch os.Args[1]{
		case "run":
			run()
		default:
			princ("help")
	}
}
fun run{
	fmt.Printf("Running %v\n",os.Args[2:])
}
func must(err error){
	if err !=null{
		panic(err)
	}
}
```

 