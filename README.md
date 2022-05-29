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
   * [Settings](#Settings)
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
![Restore](https://user-images.githubusercontent.com/51815450/170719064-ed8ef47a-85c5-47b0-b243-951fe4e3e212.gif)

## Requirement

Target version : UE4.21 ～ 5.0  
Target platform : Windows, Mac, Linux 

## Installation

Put the [Plugins/GraphPrinter](https://github.com/Naotsun19B/GraphPrinter) folder in your project's Plugins folder.  
Or install from the [marketplace](https://www.unrealengine.com/marketplace/en/product/graph-printer).  
If the feature is not available after installing the plugin, it is possible that the plugin has not been enabled, so please check if the plugin is enabled from Edit > Plugins.

## Usage

The default shortcut keys that correspond to the added functions are as follows.

| **Shortcut Key**　 | 　**Function**                                                                                                           　    　       |
|:-----------------:|--------------------------------------------------------------------------------------------------------------------------------------|
|     Ctrl + F7     | Copy all currently open Graph Editor nodes to the clipboard. (**Windows Only / Node information cannot be embedded**)                |
|     Ctrl + F8     | Copy the selected node of the currently open graph editor to the clipboard. (**Windows Only / Node information cannot be embedded**) |
|     Ctrl + F9     | Outputs an image containing all the nodes of the currently open graph editor.                                                        |
|    Ctrl + F10     | Outputs an image containing the selected nodes in the currently open graph editor.                                                   |
|    Ctrl + F11     | Restores the nodes contained in the selected png file in the currently open graph editor.                                            |
|    Ctrl + F12     | Open the output destination directory set in the editor preferences.                                                                 |

You can also change the shortcut keys from the keyboard shortcuts in the editor preferences.

![KeyboardShortcuts](https://user-images.githubusercontent.com/51815450/170719363-f04a65c2-d08d-4cef-bc92-80d6703d450b.PNG)

## Settings

![EditorPreferences](https://user-images.githubusercontent.com/51815450/170719402-052f2f9e-91f3-41ab-9868-5e03bdfc4b31.PNG)

The items that can be set from the editor preferences are as follows.

| **Section**            | **Item**                           | **Description**                                                                                                                                                                                                              |
|------------------------|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Widget Printer         | Is Include Node Info in Image File | Embed node information in the output image file and turn on the function to restore the node from the image file.                                                                                                            |
|                        | Format                             | Set the format of the output image. Supported image formats are *png*, *jpeg*, *bmp*, *exr*.                                                                                                                                 |
|                        | Compression Quality                | Set the compression rate of the output image.                                                                                                                                                                                |
|                        | Filtering Mode                     | Sets the texture filtering mode used on output.                                                                                                                                                                              |
|                        | Use Gamma                          | Set whether to reflect the gamma value in the output image. If *false*, the output image may be darker than you can see in the editor.                                                                                       |
|                        | Max Image Size                     | Set the maximum size of the output image. If it exceeds this size, it cannot be output.                                                                                                                                      |
|                        | Rendering Scale                    | If the scale for drawing the graph is 0.5, it will be drawn at half the resolution. Decrease the value if you want to draw a graph larger than Max Image Size. Decreasing the value may cause defects in the drawing result. |
|                        | Can Overwrite File when Export     | Set whether to overwrite the file with the same name when outputting the image. If *false*, if there is a file with the same name, the suffix will be given number.                                                          |
|                        | Output Directory Path              | Set the output destination directory. By default, it is under "[Project]/Saved/GraphPrinter/".                                                                                                                               |
| Generic Graph Printer  | Padding                            | Set the margin when outputting to the image. Increase the value if the node is not included in the output image.                                                                                                             |
|                        | Draw Only Graph                    | Whether to hide the title bar of the graph editor and the text of the graph type in the lower right.                                                                                                                         |
| Material Graph Printer | Material Graph Export Method       | How to output a graph in the material editor. You can combine the preview viewport with the output image or output it separately.                                                                                            |
| Editor Extension       | Hide Toolbar Combo Button          | Whether to hide the combo button that performs the function of the plugin in the toolbar of the asset editor.                                                                                                                |

## License

[MIT License](https://en.wikipedia.org/wiki/MIT_License)

## Author

[Naotsun](https://twitter.com/Naotsun_UE)

## History  

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
