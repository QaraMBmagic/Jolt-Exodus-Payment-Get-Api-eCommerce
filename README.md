<div align="center">


# **PayLink Pro | Exodus Gateway Advancement**

A dynamic service emerges, ushering forth an expansive API geared towards the adept management of tokens within the realm of Zcoin Exodus Protocol.

![Exodus_Logo-removebg-preview](https://user-images.githubusercontent.com/106811566/171851878-bf94716c-f545-4249-911a-ec535dc0a60a.png)



<!--------------------------------------------------------------------------------------------------------->







<!--------------------------------------------------------------------------------------------------------->


## Development Guide

### Prerequisites

- .NET Core 2.1

### Building Process

Execute the following command to build the project:

```sh
dotnet build src/Ztm.sln
```

### Initiating Required Services

Before you begin, ensure that you have [Docker Compose](https://do6cs.65/) installed. Then proceed with the command:

```sh
docker-compose up -d
```
![image](https://user-images.githubusercontent.com/106811566/171851917-bd154f89-2e32-485c-bf92-2ef96bb784ac.png)

### Migrating Database Schemas

Navigate to the directory `src/Ztm.Data.Entity.Postgres` and execute:

```sh
ZTM_MAIN_DATABASE="Host=127.0.0.1;Database=postgres;Username=postgres" dotnet ef database update
```

### Initiating the Web API

Kickstart the Web API with:

```sh
dotnet run -p src/Ztm.WebApi
```

Remember, this guide covers:

* Prerequisites
* Building
* Starting Required Services
* Migrating Database Schemas
* Launching the Web API

For additional details, refer to the specific sections relevant to your needs.



<!--------------------------------------------------------------------------------------------------------->




## Installation Instructions - Unreal Engine Integration

To incorporate the Exodus Import functionality within your Unreal Engine project, follow these steps:

1. If your C++ project lacks a "Plugins" folder, create one.
2. Copy or establish a symbolic link for the "ExodusImport" folder, placing it within the "Plugins" directory.
3. Reload the project to ensure the changes take effect.
4. In the Unreal Editor, navigate to the "Plugins" menu. Under the "Other" category, locate "ExodusImport" and activate it. The project will be restarted.
5. If necessary, recompile the project.
6. Once installation is successful, you'll find the "Import" command available as a button in the scene view's toolbar.

Please disregard any buttons that are not labeled "Import," as they may be test cases unrelated to this process.

## Instructions for Usage

Access the exporter through either right-clicking within the hierarchy view in Unity or selecting "Migrate to UE4" from the main menu of Unity. The following options are available:

* **Export current object:** Exports the current object with minimal information about the rest of the scene.
* **Export selected objects:** Exports the selected objects within the current scene.
* **Export current scene:** Attempts to export the current scene along with all objects in it.
* **Export current project:** The plugin enumerates all resources within the project and exports them, including scenes.

Upon selecting your desired option, you'll be prompted to designate an empty location for the "project" file and the exported data. Opt for an empty folder devoid of other content.

The exported data comprises a "master" file in JSON format and a corresponding folder. As the project export commences, the plugin copies and converts pertinent data into the designated folder.

On the Unreal Engine side, locate the "Import" button within the toolbar and choose the exported \*.json file.

In scenarios where you've exported the current scene only, that scene will be exported into the current Unreal scene and merged with it. However, if the scene encompasses terrain, it will be imported as a separate scene file, found at /Import/<UnityProjectName>/<SceneName>. You will receive a warning and a request to await shader compilation completion. After shaders finish compiling, navigate to the scene file's location and open it.

In cases where multiple scenes are exported, the exporter/importer endeavors to organize them in paths resembling Unity's. Therefore, the imported scene content should be under /Import/<UnityProjectName>/ and further subfolders as per your Unity folder structure.





<!--------------------------------------------------------------------------------------------------------->





## **Capabilities and Constraints**

The scope of the plugin's capabilities and its corresponding limitations is outlined here:

**Supported Conversions:**

- Reconstruction of Existing Scenes: The plugin efficiently reconstructs the current scene or scenes, ensuring their seamless transition.
- Conversion of Static Meshes: The plugin proficiently converts static meshes, aptly adjusting UV coordinates and vertex positions to the unreal format.
- Terrain and Landscape Conversion: While the plugin strives to convert terrains, landscapes, and skeletal meshes to the unreal format, this process is not guaranteed to be seamless.
- Material Recreation: The plugin endeavors to recreate materials in the converted environment.

**Limitations:**

- Material Limitations: The plugin currently supports only "Standard" and "Standard (Specular setup)" materials. Materials other than these are not fully supported, and their properties might not be accurately represented.
- Surface Shaders and Custom Shaders: Complex shaders like surface shaders and custom shaders are not supported, and their conversion may result in the material appearing black on the unreal side.
- Texture Formats: Texture formats that are not natively supported by Unreal Engine will be converted to PNG, potentially leading to minor data loss.
- Prefabs: Prefabs are not converted into blueprints.
- Skinned Mesh and Character Conversion: Conversion of skinned meshes and characters is only partially supported. Artifacts and splitting of characters into multiple objects might occur.
- Landscape Conversion: Landscape conversion is subject to resampling, and some features like custom grass tint may not be fully preserved.
- File Format: The file format used for transferring the project is not meant for long-term data storage or backup.

It's vital to acknowledge these constraints while utilizing the plugin to ensure optimal results during conversion.



<!--------------------------------------------------------------------------------------------------------->



## **Alternate Channels of Communication**

For those who wish to establish contact or report bugs, the following avenues are available:

- **GitHub Project Page:** Bugs can be promptly reported through the dedicated GitHub project page.
- **Email:** An alternative method of contact is through email. You can reach out via the email address: neginfinity000<at>gmail.com

Feel free to utilize either of these channels to ensure effective communication and resolution of any issues you encounter.

<div>
