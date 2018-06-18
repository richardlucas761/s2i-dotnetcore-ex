# richardlucas761notes.md

Notes on creating my first OpenShift application.

## Build failed on first test

I created a new Open Shift application in the Starter environment from the source code at my fork https://github.com/richardlucas761/s2i-dotnetcore-ex of the sample at https://github.com/redhat-developer/s2i-dotnetcore-ex but I must have something wrong with the configuration because I'm getting this build error:

```
Cloning "https://github.com/richardlucas761/s2i-dotnetcore-ex " ...
	Commit:	0543be02d0be779d08e6c43f82ef9f0610f5d4e3 (Update for .NET Core 2.0 release. (#32))
	Author:	Severin Gehwolf <jerboaa@gmail.com>
	Date:	Mon Aug 21 18:00:03 2017 +0200
Pulling image "registry.access.redhat.com/dotnet/dotnet-20-rhel7@sha256:5a9a19365c3464dd5fba786c59808bfc75a9e7a32f92072e8626c3a84d68eb33" ...
Using SDK: 2.0.3
---> Copying application source ...
error: DOTNET_STARTUP_PROJECT has no project file
You can specify the startup project by adding an '.s2i/environment' file to the source repository.
The source repository contains the following projects:
- app/app.csproj
Update the '.s2i/environment' file to specify the project you want to publish, for example DOTNET_STARTUP_PROJECT=app/app.csproj.
error: build error: non-zero (13) exit code from registry.access.redhat.com/dotnet/dotnet-20-rhel7@sha256:5a9a19365c3464dd5fba786c59808bfc75a9e7a32f92072e8626c3a84d68eb33
```

I tried adding a new environment variable called "DOTNET_STARTUP_PROJECT" with a value of "app/app.csproj" but the build was still broken with the same error.

## Tried the sample build and that worked okay

I couldn't figure out what the issue was with my forked branch of the default sample at https://github.com/redhat-developer/s2i-dotnetcore-ex so I tried using that repository instead.

That worked and I was able to deploy from that GIT repository although I don't understand what the difference is between this repository and my fork?

There must be something else involved I don't understand yet.
