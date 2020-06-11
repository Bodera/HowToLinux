# Razor pages

This is a compilation of the tutorial provided at the [MS Web apps with ASP .NET documentation](https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/?view=aspnetcore-3.1) regarding to Razor Pages.

Razor Pages is a *Model-View-View-Model* based web-framework. It's an alternative to ASP .NET *Model-View-Control*.

The tools listed below are a prerequisite to accomplish this tutorial.

* Visual Studio Code
* C# for Visual Studio Code (latest version)
* .NET Core 3.1 SDK or later

Retake from [here](https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start?view=aspnetcore-3.1&tabs=visual-studio-code#create-a-razor-pages-web-app).

Initialize the default webapp

```bash
mkdir razorpages-webapps
cd razorpages-webapps
dotnet new webapp -o RazorPagesMovie
code -r RazorPagesMovie
```

A pop-up window with a dialog asks `Required assets to build and debug are missing from 'RazorPagesMovie'. Add them?` Select `Yes`.

In order to run the app just run `F5` on the project folder from Visual Studio Code.
