# suave-corert

This repo intends to debug/implement a simple [Suave](https://suave.io) webserver along with [CoreRT](https://github.com/dotnet/corert) compiler.

## How to run

- Using Docker

```bash
> docker build -t suave-corert .
> docker run suave-corert 
```

- Using Dotnet (Requires .Net Core)

```bash
> dotnet publish -r <RID> -c <Configuration> -o outside
> ./outside/Simple-Web
```

Detailed information about publish command, check [this](https://github.com/dotnet/corert/blob/master/samples/HelloWorld/README.md#restore-and-publish-your-app).

## Expected Output

```bash
Smooth! Suave listener started in 52.826ms with binding 127.0.0.1:8080
```

## Current Output

```bash
Unhandled Exception: System.ArgumentNullException: Value cannot be null. Parameter name: path1
   at System.IO.Path.Combine(String, String) + 0x53
   at Suave.Web.startWebServerAsync(SuaveConfig, FSharpFunc\`2) + 0x46
   at Suave.Web.startWebServer(SuaveConfig, FSharpFunc\`2) + 0x17
   at Program.main(String[]) + 0x28
   at Simple-Web!<BaseAddress>+0x7d639d
Aborted
```
