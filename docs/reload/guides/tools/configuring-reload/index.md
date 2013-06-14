<!-- <mosyncheadertags>
<meta name="description" content="Configuring MoSync Reload" />
<meta name="keywords" content="mobile development,dev,sdk,ide,apps,mobile,apps,android,ios,iphone,ipad,mobile,open source,application,ide,cross
platform,programming,mosync,,reload,mosync reload,native ui,nativeui" />
<title>Configuring MoSync Reload</title>
</mosyncheadertags> -->

# Configuring Reload

This guide shows various options available for configuring the Reload Server.

## Reload installation file structure

This section gives an overview of the installation structure of Reload.

On Windows and Linux, Reload is installed by unpacking the download package to the file system, using the directory of your choise. The Reload Server files are found in:

    <install-dir>/server/

On OS X, Reload is installed into the Applications system folder. The Reload Server files are found in: 

    /Applications/Reload.app/Contents/Resources/

Knowing the location of the installed server is important if you wish to use the server command line options, or change the server settings in file globals.js.

## Command line options

You can start the Reload Server using command line options. Launch the file *main.js* in the server installation using nodejs. Provide desired options on the command line.

Options available are:

* **-nobrowser** Start Reload Server without launching the Development UI
* **-debug** Enable debug logging, write debugg information to stdout

Starting the Reload Server without automatically launching the Development UI is useful when you wish to use Reload with a different browser than your default browser, or when you wish to run the server on a remote machine.

To start the server using command line options, you must launch it from the Reload Server directory. On Windows and Linux, this is **<install-dir>/server**. On OS X, this is folder **/Applications/Reload.app/Contents/Resources/**

For example, on Windows, to start the Reload Server without automatically launching the Development UI, use the following option:

    cd server
    bin\win\node.exe main.js -nobrowser

And to start the Reload Server with debug logging enabled, use the following option: 

    cd server
    bin\win\node.exe main.js -debug

On Windows, you can modify the file *ReloadLauncher.bat* to include the prefered command line options. On OS X the corresponding file is named *script*.

Note that the Reload Server and the Weinre inspector/debugger are launched separately. If you launch the Reload Server manually, also must also manually launch Weinre, if you wish to use it.

As an illustration of what happens when Reload is launched, let us look at the file ReloadLauncher.bat:

    cd server
    start bin\win\node.exe node_modules\weinre\weinre --boundHost -all-
    start bin\win\node.exe main.js
    cd ..

This file is used on Windows to launch the Reload Server an Weinre.

## Run Reload Server on a remote machine

You can now run the Reload Server on one machine and use the Development UI from another machine. This means you can host the server on a remote machine, so you do not have to run it locally. However, the most common option for developers would probably still be to run the server and Development UI on the same machine, and this is the configuration that is supported out-of-the-box when you install the Reload Server.

## Configuring the Example Gallery

The configuration file **globals.js** contains various settings used by the Reload Server.

This file is fond in the **application** directory of the Reload installation:

* **Windows:** <install-dir>/server/application/globals.js
* **Linux:** <install-dir>/server/application/globals.js
* **OS X: /Applications/Reload.app/Contents/Resources/application/globals.js

You can configure the setting used to fetch example projects to show in the Development UI. The example gallery is dynamically loaded from the [MoSyncSamples](https://github.com/MoSyncSamples) GitHub repository. 

Update this line in globals.js to point to your own GitHub account:

   sampleProjectsFeedUrl: "https://api.github.com/orgs/MoSyncSamples/repos",
