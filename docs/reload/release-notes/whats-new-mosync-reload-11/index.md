<!-- <mosyncheadertags>
<meta name="description" content="MoSync Reload 1.1 Release Notes." />
<meta name="keywords" content="mobile development,dev,sdk,ide,apps,mobile,apps,android,ios,iphone,ipad,mobile,open source,application,ide,cross
platform,programming,mosync,,reload,mosync reload,native ui,nativeui" />
<title>What's New in MoSync Reload 1.1</title>
</mosyncheadertags> -->

<style>
.screenshot
{
  width: 240px;
  height: 400px;
}
</style>

# What's New in MoSync Reload 1.1

## Summary of new features

The release of MoSync Reload 1.1  includes new Reload Client app, improved Reload Server functionality, a new command line tool, and several other improvements.

Download the new Reload installation package from the [MoSync Reload download page](http://www.mosync.com/download/reload).

The following is a summary of what is new in MoSync Reload 1.1:

* **New Reload Client app** - New UI and new features such as automatic server discovery.
* **Updated Development UI** - Improved workbench, new gallery of example apps, and a highlight hint help system.
* **Updated Reload Server** - Run server on remote machine, new command line options.
* **Command line tool for Reload** - Allows you to script the Reload Server and integrate Reload functionality with your existing development tools.

## New Reload Client App

Reload 1.1 includes a new Reload Client app with a new UI and new functionality. This app can be downloaded from the app stores (iOS, Android, Windows Phone), for easy installation on your devices. The new Reload Client is also included in the [MoSync Reload download](http://www.mosync.com/download/reload).

Summary of new features in the app:

* Automatic scanning for servers, using server discovery (no need to manually type in IP-addresses).
* Browsing projects on the server.
* Support for saving projects locally.
* Launching saved projects (works when you are not connected to the server).
* Reloading projects directly from the app (alternative to reloading from the Developer UI).

Read more about these new features in the [Reload Client guide](TEMPLATE_DOC_PATH/reload/guides/tools/reload-client-app/index.html).

## Updated Development UI

The Reload Development UI has been updated with several new features.

### Improved Workbench

The JavaScript Workbench has been updated to be integrated with the Log message view (the Log tab has been removed). This makes it much easier to inspect the log while you are using the Workbench, since you do not have to switch between tabs. You can also resize the Log message view to use the entire viewing area if needed.

Go to the guide [JavaScript Workbench](TEMPLATE_DOC_PATH/reload/guides/tools/using-javascript-workbench/index.html) for more details and code examples that show what you can do with the Workbench.

### New Example Gallery

The Development UI has a new tab with a gallery of HTML5/JS example apps. This gallery includes new apps such as the MoBlocks game, and more examples will be added over time.

You can copy apps in the gallery to your local workspace, or directly reload apps on connected devices. In this way, you can both quickly try out the examples, and import examples to further explore and work with them.

The example gallery is dynamically loaded from the [MoSyncSamples](https://github.com/MoSyncSamples) GitHub repository.

If you are into experimenting, you can configure Reload to use a custom GitHub repository. This is done in the file **application/globals.js**, which is found in the Reload Server directory. Consult the guide [Configuring Reload](TEMPLATE_DOC_PATH/reload/guides/tools/configuring-reload/index.html) for further details.

### Highlight hint help system

The Reload Development UI has a new hint help system, which highlights the specific parts of the user interface needed to complete a command.

For example, if you press the "Reload" button without having selected a project, the list of projects is highlighted and a help message is shown, which makes it instantly clear that a project needs to be selected to do a reload.

The previous help system used popup dialog messages, which were not as clear and direct as the highlight hints.

## Updated Reload Server

### Run Reload Server on a remote machine

You can now run the Reload Server on one machine and use the Development UI from another machine. This means you can host the server on a remote machine, so you do not have to run it locally. However, the most common option for developers would probably still be to run the server and Development UI on the same machine, and this is the configuration that is supported out-of-the-box when you install the Reload Server.

### Command line options

New in this version of the Reload Server is support for command line options.

Options are:

* **-nobrowser** Start Reload Server without launching the Development UI

* **-debug** Enable debug logging

Starting the Reload Server without automatically launching the Development UI is useful when you wish to use Reload with a different browser than your default browser, or when you wish to run the server on a remote machine.

To learn about how to use the command options, consult the guide [Configuring Reload](TEMPLATE_DOC_PATH/reload/guides/tools/configuring-reload/index.html).

## Command Line Tool for Reload

This release of Reload contains a new command line tool, which you can use to script Reload (note that this is not the same thing as the command line options for the Reload Server).

Using the Command Line Tool you can control the Reload Server from the command line, create scripts to perform Reload tasks, and integrate Reload with existing development tools.

With this tool, you can:

* Reload projects
* Create new projects
* Change workspace
* List projects in the workspace
* List connected devices

The Command Line Tool currently assumes the Reload Server is running on the same machine. In future versions, a parameter will be added to allow scripting of servers running on remote machines.

Read more in the [Command line tool user guide](TEMPLATE_DOC_PATH/reload/guides/tools/reload-command-line-tool/index.html).

<!-- **TODO: Guide for sublime plugin?** -->

## Known Limitations

Automatic server discovery in the Reload Client is only supported on Android and iOS, since Windows Phone do not have broadcast support.

List of [known issues in Reload 1.1](http://jira.mosync.com/secure/IssueNavigator.jspa?mode=hide&requestId=11220).

If you have projects created with an old version of Reload, make sure to update them. Specifically, you need to update the file <b>wormhole.js</b> to the latest version. Please read the [Wormhole Upgrade Guide](TEMPLATE_DOC_PATH/sdk/js/guides/wormhole/update-wormhole/index.html) for further details.

## Fixed Bugs

List of [bugs fixed in Reload 1.1](http://jira.mosync.com/secure/IssueNavigator.jspa?mode=hide&requestId=11221).
