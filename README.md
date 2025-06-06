# GraphPrinter

![Plugin](https://user-images.githubusercontent.com/51815450/170719311-8dd70514-ef6b-4649-82bd-6be9232ae16e.PNG)

<!--ts-->
   * [Description](#Description)
      * [On the editor](#on-the-editor)
      * [Output image](#output-image)
      * [Node restore](#node-restore)
   * [Requirement](#Requirement)
   * [Installation](#Installation)
   * [Usage](#Usage)
     * [Stream Deck](#stream-deck)
   * [Settings](#Settings)
   * [Note](#Note)
   * [License](#License)
   * [Author](#Author)
   * [History](#History)
<!--te-->

## Description

This plugin adds a shortcut key that prints an Unreal Engine graph editor (such as Blueprint or Material ...) to an image file or copies it to the clipboard.
As shown in the image below, you can also output the part that is not displayed in the graph editor to the image file.
You can also restore the node from the output image file.  

#### On the editor
![BeforeExport](https://user-images.githubusercontent.com/51815450/170719166-b02a5526-d052-404c-bb13-d888ad7c080f.PNG)

#### Output image
![BP_Sky_Sphere-RefreshMaterial](https://user-images.githubusercontent.com/51815450/170719253-f5365b35-e86c-4b1a-ac0a-7b3f425c050f.png)

#### Node restore  
https://user-images.githubusercontent.com/51815450/177288939-0ad344d9-fe39-4e44-bff7-1b7037793517.mp4

## Requirement

Target version : UE4.27 ~ 5.6  
Target platform : Windows, Mac, Linux 

## Installation

Put the [Plugins/GraphPrinter](https://github.com/Naotsun19B/GraphPrinter) folder in your project's Plugins folder.  
Or install from the [marketplace](https://www.unrealengine.com/marketplace/en/product/graph-printer).  
If the feature is not available after installing the plugin, it is possible that the plugin has not been enabled, so please check if the plugin is enabled from Edit > Plugins.

## Usage

The default shortcut keys that correspond to the added functions are as follows.

| **Shortcut Key**　 | 　**Function**                                                                                                           　    　 |
|:-----------------:|--------------------------------------------------------------------------------------------------------------------------------|
|     Ctrl + F6     | Collects widgets supported by any printer from the currently displayed screen.                                                 |
|     Ctrl + F7     | Copies the entire currently selected widget to the clipboard. (**Node information cannot be embedded**)                        |
|     Ctrl + F8     | Copies the selected part of the currently selected widget to the clipboard. (**Node information cannot be embedded**)          |
|     Ctrl + F9     | Exports an image containing the entirety of the currently selected widget.                                                     |
|    Ctrl + F10     | Exports an image containing the selected portion of the currently selected widget.                                             |
|    Ctrl + F11     | Restores the state of the widgets contained in the selected image file to the currently selected widget.                       |
|    Ctrl + F12     | Opens the output destination directory set in the editor preferences.                                                          |

You can also change the shortcut keys from the keyboard shortcuts in the editor preferences.  

![KeyboardShortcuts](https://user-images.githubusercontent.com/51815450/170719363-f04a65c2-d08d-4cef-bc92-80d6703d450b.PNG)

You can also call the function from the tool menu or the asset editor toolbar.  

![ToolMenu](https://user-images.githubusercontent.com/51815450/225569724-e150c60c-631a-4818-bf2a-9c831be2a157.png)
![Toolbar](https://user-images.githubusercontent.com/51815450/225569744-1befb4bc-12f5-464a-a125-1e5c13aa7967.png)

|     **Category**　      | 　**Item**                                 | **Function**                                                                                             |
|:----------------------:|-------------------------------------------|----------------------------------------------------------------------------------------------------------|
|         TARGET         | Collect Target Widgets                    | Collects widgets supported by any printer from the currently displayed screen.                           |
|   COPY TO CLIPBOARD    | Copy All Area Of Widget To Clipboard      | Copies the entire currently selected widget to the clipboard.                                            |
|                        | Copy Selected Area Of Widget To Clipboard | Copies the selected part of the currently selected widget to the clipboard.                              |
|  EXPORT TO IMAGE FILE  | Print All Area Of Widget                  | Exports an image containing the entirety of the currently selected widget.                               |
|                        | Print Selected Area Of Widget             | Exports an image containing the selected portion of the currently selected widget.                       |
| IMPORT FROM IMAGE FILE | Restore Widget From Image File            | Restores the state of the widgets contained in the selected image file to the currently selected widget. |
|         OTHER          | Open Export Destination Folder            | Opens the output destination directory set in the editor preferences.                                    |
|                        | Open Plugin Settings                      | Opens the setting screen for each function.                                                              |
|                        | Install Stream Deck Plugin                | Installs the Graph Printer plugin for Stream Deck into the Stream Deck application.                      |

### Stream Deck

![StreamDeckApplication](https://user-images.githubusercontent.com/51815450/225564031-6e183445-9777-4c52-80f5-337c8f6e1ad8.PNG)

This plugin supports calling functions from Stream Deck.  

Follow the steps below to use the feature.  

1. Install the Graph Printer plugin for Stream Deck from the Tools menu or `Install Stream Deck Plugin` from the toolbar.  
2. Place buttons for the functions you want to use in the Stream Deck application.  
3. Set the server URL to the `Server URL` property of the placed button. (You can leave it as default)  
4. Set the same server URL as the Stream Deck side in the `Server URL` of `Graph Printer - Remote Control` in the editor preferences. (You can leave it as default)  
5. You can connect to the Stream Deck by setting `Enable Remote Control` in `Graph Printer - Remote Control` in the editor preferences to `true`.  
6. Press the button placed from the Stream Deck.  

## Settings

![EditorPreferences](https://user-images.githubusercontent.com/51815450/170719402-052f2f9e-91f3-41ab-9868-5e03bdfc4b31.PNG)

The items that can be set from the editor preferences are as follows.

| **Section**            | **Item**                                 | **Description**                                                                                                                                                                                                              |
|------------------------|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Widget Printer         | Is Include Widget Info in Image File     | Embed widget information in the output image file and turn on the function to restore the widget state from the image file.                                                                                                  |
|                        | Format                                   | Set the format of the output image. Supported image formats are *png*, *jpeg*, *bmp*, *exr*.                                                                                                                                 |
|                        | Compression Quality                      | Set the compression rate of the output image.                                                                                                                                                                                |
|                        | Filtering Mode                           | Sets the texture filtering mode used on output.                                                                                                                                                                              |
|                        | Use Gamma                                | Set whether to reflect the gamma value in the output image. If *false*, the output image may be darker than you can see in the editor.                                                                                       |
|                        | Max Image Size                           | Set the maximum size of the output image. If it exceeds this size, it cannot be output.                                                                                                                                      |
|                        | Rendering Scale                          | If the scale for drawing the graph is 0.5, it will be drawn at half the resolution. Decrease the value if you want to draw a graph larger than Max Image Size. Decreasing the value may cause defects in the drawing result. |
|                        | Can Overwrite File when Export           | Set whether to overwrite the file with the same name when outputting the image. If *false*, if there is a file with the same name, the suffix will be given number.                                                          |
|                        | Output Directory Path                    | Set the output destination directory. By default, it is under "[Project]/Saved/GraphPrinter/".                                                                                                                               |
| Generic Graph Printer  | Padding                                  | Set the margin when outputting to the image. Increase the value if the node is not included in the output image.                                                                                                             |
|                        | Draw Only Graph                          | Whether to hide the title bar of the graph editor and the text of the graph type in the lower right.                                                                                                                         |
| Material Graph Printer | Material Graph Export Method             | How to output a graph in the material editor. You can combine the preview viewport with the output image or output it separately.                                                                                            |
| Details Panel Printer  | Padding                                  | Height margin when drawing the details view.                                                                                                                                                                                 |
|                        | Is Include Expansion State In Image File | Whether to embed the expanded state of each item in the image file and restore the expanded state of each item when restoring.                                                                                               |
|                        | Whether To Also Restore Expanded States  | Whether to also restore the expanded state when restoring.                                                                                                                                                                   |
| Remote Control         | Enable Remote Control                    | Whether remote control via web socket is enabled. Please check again when the server is rebuilt.                                                                                                                             |
|                        | ServerURL                                | Your server URL. You can use ws, wss or wss+insecure. Disable remote control once to edit.                                                                                                                                   |
| Editor Extension       | Show Sub Menu In Tool Menu               | Whether to display submenus that perform plugin functions in the editor's tools menu.                                                                                                                                        |
|                        | Show Combo Button In Toolbar             | Whether to show the combo button that performs the function of the plugin in the toolbar of the asset editor.                                                                                                                |
|                        | Show Combo Button In StatusBar           | Whether to show the combo button that performs the function of the plugin in the editor's status bar.                                                                                                                        |
|                        | Collect Target Widgets Automatically     | Whether to automatically collect the target widgets when opening any type of menu.                                                                                                                                           |

## Note

・When copying to the clipboard, widget information cannot be embedded.  
・Features related to the details panel are not available for engine versions prior to UE 5.0 and Mac platforms.  
・Stream Deck functionality is currently only available on Windows platforms.  
・The menu for installing the Stream Deck plugin will not appear if the Stream Deck application is not installed.  

## License

[MIT License](https://en.wikipedia.org/wiki/MIT_License)

## Author

[Naotsun](https://twitter.com/Naotsun_UE)

## History  

- (2025/06/06) v2.9  
  Added support for UE5.6  
  Fixed a bug where editor preference was not saved correctly  

- (2025/03/16) v2.8  
  Added support for UE5.5  
  Support before UE4.26 has been discontinued  

- (2024/06/25) v2.7  
  Fixed a bug where plugin functions could not be used from the menu  
  Added a function that displays a list of widgets to be processed in the menu and allows you to select which widget to process  

- (2024/04/24) v2.6   
  Added support for UE5.4  
  Copy to clipboard function now works on Mac and Linux  
  Added plugin menu to status bar  
  You can now change whether to display plugin menus in the tool menu, toolbar, and status bar from the editor preferences

- (2023/09/07) v2.5  
  Added support for UE5.3
  Plugin settings in editor preferences are now saved common to all projects

- (2023/05/17) v2.4  
  Added support for UE5.2  

- (2023/03/16) v2.3  
  Set icons for each function  
  Added the ability to call plugin functions from the outside using web sockets  
  Added export import function for details panel  
  Enabled to call functions from Stream Deck  

- (2022/11/08) v2.2   
  Added support for UE5.1  

- (2022/05/27) v2.1   
  Enabled to execute the function from the toolbar or tool menu
  Added the function to output the preview viewport when outputting the material graph  
  Significantly improved plugin modules and classes

- (2021/12/25) v2.0   
  Added an option to hide the title bar etc. of the graph editor

- (2021/11/28) v1.9   
  Fixed compilation error in UE 4.27 on Linux environment

- (2021/10/20) v1.8   
  Added support for UE5  

- (2021/07/11) v1.7   
  Added a shortcut key to copy the image of Graph Editor to the clipboard (**Windows Only**)  

- (2021/05/28) v1.6   
  Changed so that the asset name is included in the file name when the reference viewer is output

- (2021/05/05) v1.5   
  Corrected the problem that the image output for the first time after starting the engine becomes whitish

- (2021/04/15) v1.4   
  Added the function to embed node information in an image file and restore the node from the image file

- (2021/03/08) v1.3   
  ~~Corrected the problem that the image output for the first time after starting the engine becomes whitish~~

- (2021/01/21) v1.2   
  Changed module type to EditorNoCommandlet as a countermeasure against errors when packaging

- (2021/01/12) v1.1   
  Added the ability to limit the output size as it crashes when outputting a huge graph

- (2020/12/06) v1.0   
  Publish plugin
