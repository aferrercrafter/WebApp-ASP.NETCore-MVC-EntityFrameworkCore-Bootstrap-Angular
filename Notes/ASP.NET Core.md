__What it is__

* Complete re-write of the platform
* Cross-Platform and open source
* Single platform for MVC and Web API
* Everything is a dependency
* Low memory footpring
* Multiple deployment support _Cloud, IIS, Self-Hosting, etc_

__Frameworks supports__

* NET 4.x
    - The .NET that you have always known
    - Limited to Windows Only
* NET Core
    - The cross-platform, Net Framework
    - Linux, MAC and Windows support

__Completely Composed__

* __Above the .NET Core layer everything is a Package__
    - Frameworks are the boostrap and the CLR
    - MVC, Logging, Idenity are just packages
    - Everything is optional

__Embraces Open Web Development__

* NPM for tooling support
* Bower/NPM for client-side libraries
* Grunt and Gulp for build automation
* Nuger for .NET packages
* None of this is required

__Deployment options__

* Windows
    - Directly on Hardware
    - In a VM
    - In a Container
    - Cloud Hosting
* Linux
    - Directly on Hardware
    - In a VM
    - In a Container
    - Cloud Hosting
* Mac
    - Directly on Hardware

###Startup Configuration###

```C#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
        {
            app.Run(async (context) =>
            {
                await context.Response.WriteAsync("Hello World!");
            });
        }
```
It does not wrap up in html magically. It does exactly that, return text "Hello World", not matter the route either

```C#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
        {
            app.UseStaticFiles();
        }
```
Enable static file serving. By default, serve only the files under wwwroot folder

```C#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
        {
            app.UseDefaultFiles();
        }
```
Enable default file mapping on the current path. Default files like index.html. Can be configured

```C#
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
        {
            app.UseStaticFiles();
            app.UseDefaultFiles();
        }
```
Does not bring index.html by default. Order matters.

