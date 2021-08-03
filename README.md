# React WebView App
Desktop app built with Typescript, React, ASPNET Core and WebView2

# Notes
Use Evergreen WebView2 Runtime. Original article: https://itnext.io/write-a-desktop-app-with-react-typescript-asp-net-core-and-webview2-3a15daef4d64.

WebView2 on a Windows Forms application and spin an instance of ASP.NET Core with Kestrel.

# Steps
## 1. Create react app using vs template
```
dotnet new react -o my-new-app
cd my-new-app
dotnet build
dotnet run
```

## 2. Use typescript
```
rmdir ClientApp -force -recurse
npx create-react-app client-app --template typescript
```

## 3. Add WebView2 package
```
dotnet add package Microsoft.Web.WebView2
```

## 4. Change .csproj to output an .exe
```
<TargetFramework>net5.0-windows</TargetFramework>
<OutputType>WinExe</OutputType>
<UseWindowsForms>true</<UseWindowsForms>
```

## 5. Add windows form file (and designer)

## 6. Make some changes to Program.cs to run the windows form on load

## 7. Build the app
```
dotnet restore "./my-new-app.csproj" --runtime win-x64
```

## 8. Publish the app
```
dotnet publish "my-new-app.csproj" -c Release -o ./publish --no-restore --runtime win-x64 --self-contained true /p:PublishTrimmed=true /p:PublishSingleFile=true
```