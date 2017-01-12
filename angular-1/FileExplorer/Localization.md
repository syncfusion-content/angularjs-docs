---
layout: post
title: Localization
description: localization support
platform: Angular-1
control: File Explorer
documentation: ug
---


# Localization

The FileExplorer control provides the translations for all static texts and messages. By default the FileExplorer uses the US English (en-US) language, and it having the built-in values of all texts with the corresponding key.

The below table lists out the keys with corresponding texts in English culture.

{% highlight javascript %}

        ej.FileExplorer.Locale["en-US"] = {
            		
		    Back: "Backward",

            Forward: "Forward",

            Upward: "Upward",

            Refresh: "Refresh",

            Addressbar: "Address bar",

            Upload: "Upload",

            Rename: "Rename",

            Delete: "Delete",

            Download: "Download",

            Error: "Error",

            Cut: "Cut",

            Copy: "Copy",

            Paste: "Paste",

            Details: "Details",

            Searchbar: "Search bar",

            Open: "Open",

            Search: "Search",
			
			EmptyResult:"No items match your search",
			
			EmptyFolder: "This folder is empty",

            NewFolder: "New Folder",

            Size: "Size",

            RenameAlert: "Please enter new name",

            NewFolderAlert: "Please enter new folder name",

            ContextMenuOpen: "Open",

            ContextMenuNewFolder: "New Folder",

            ContextMenuDelete: "Delete",

            ContextMenuRename: "Rename",

            ContextMenuUpload: "Upload",

            ContextMenuDownload: "Download",

            ContextMenuCut: "Cut",

            ContextMenuCopy: "Copy",

            ContextMenuPaste: "Paste",

            ContextMenuGetinfo: "Get info",

            ContextMenuRefresh: "Refresh",

            Item: "item",

            Items: "items",

            ErrorOnFolderCreation: "This destination already contains a folder named '{0}'. Do you want to merge this folder content with already existing folder '{0}'?",

            GeneralError: "Please see browser console window for more information",

            ErrorPath: "FileExplorer can't find '{0}'. Check the spelling and try again.",

            ReplaceAlert: "File named '{0}' already exists. Replace old file with new one?",

            DuplicateAlert: "There is already a file with the same name '{0}'. Do you want to create file with duplicate name",

            DuplicateFileCreation: "There is already a file with the same name in this location. Do you want to rename '{0}' to '{1}'?",

            DeleteFolder: " Are you sure you want to delete ",

            DeleteMultipleFolder: "Are you sure you want to delete these {0} items?",

            CancelPasteAction: "The destination folder is a subfolder of source folder.",

            OkButton: "Ok",

            CancelButton: "Cancel",

            YesToAllButton: "Yes to all",

            NoToAllButton: "No to all",

            YesButton: "Yes",

            NoButton: "No",

            Grid: "Grid View",

            Tile: "Tile View",

            Name: "Name",

            Location: "Location",

            Type: "Item type",

            Created: "Created",

            Accessed: "Accessed",

            Modified: "Modified",

            DialogCloseToolTip: "close",

            UploadSettings: {

                buttonText: {

                    upload: "Upload",

                    browse: "Browse",

                    cancel: "Cancel",

                    close: "Close"

                },

                dialogText: {

                    title: "Upload Box",

                    name: "Name",

                    size: "Size",

                    status: "Status"

                },

                dropAreaText: "Drop files or click to upload",

                filedetail: "The selected file size is too large. Please select a file within the valid size.",

                denyError: "Files with #Extension extensions are not allowed.",

                allowError: "Only files with #Extension extensions are allowed.",

                cancelToolTip: "Cancel",

                removeToolTip: "Remove",

                retryToolTip: "Retry",

                completedToolTip: "Completed",

                failedToolTip: "Failed",

                closeToolTip: "Close"

            }

        };

{% endhighlight %}

## Change the Culture

The language of the FileExplorer can be changed by the [locale](http://help.syncfusion.com/api/js/ejfileexplorer#members:locale) property. This property allows the culture code of the country as input. The culture code has to specify in the standard format as ** [Language Code]-[County/Region Code]**. 

For example the culture code for Spanish is **es-ES**.

You can customize built-in text and messages based on your culture. The below example shows the usage of FileExplorer with German (de-DE) culture. 

{% highlight javascript %}

        ej.FileExplorer.Locale["es-ES"] = {
        EmptyResult: "Ningun articulo concuerda con su busqueda",
        EmptyFolder: "Esta carpeta est� vac�a",
        ProtectedFolder: "Sie ist nicht die Berechtigung diesen Ordner zugreifen",
        Back: "hacia atr�s",
        Forward: "adelante",
        Upward: "Hacia arriba",
        Refresh: "refrescar",
        Addressbar: "Barra de direcci�n",
        Upload: "Subir",
        Rename: "rebautizar",
        Delete: "borrar",
        Download: "Descargar",
        Error: "error",
        Cut: "cortada",
        Copy: "copia",
        Paste: "pasta",
        Details: "Detalles",
        Searchbar: "barra de b�squeda",
        Open: "abierto",
        Search: "busqueda",
        NewFolder: "Nueva Carpeta",
        SelectedFileUrl: "direcci�n Web",
        SelectedFileName: "t�tulo",
        ImageWidth: "ancho",
        ImageHeight: "altura",
        Insert: "Insertar",
        Cancel: "cancelar",
        RenameAlert: "Por favor, introduzca el nuevo nombre",
        NewFolderAlert: "Introduzca el nuevo nombre de la carpeta",
        ContextMenuOpen: "abierto",
        ContextMenuNewFolder: "nueva carpeta",
        ContextMenuDelete: "borrar",
        ContextMenuRename: "rebautizar",
        ContextMenuUpload: "Subir",
        ContextMenuDownload: "descargar",
        ContextMenuCut: "cortada",
        ContextMenuCopy: "copia",
        ContextMenuPaste: "pasta",
        ContextMenuGetinfo: "Obt�n informaci�n",
        ContextMenuRefresh: "refrescar",
        ContextMenuOpenFolderLocation: "Ubicaci�n de la carpeta abierta",
        ContextMenuSortBy: "Ordenar por",
        SortBy: "Ordenar por",
        Item: " art�culo",
        Items: " art�culos",
        Selected: "seleccionado",
        Permission: "Permiso",
        OkButton: "Okay",
        CancelButton: "cancelar",
        YesButton: "s�",
        NoButton: "No",
        YesToAllButton: "Si a todo",
        NoToAllButton: "No a todos",
        Size: "tama�o",
        Grid: "Vista de cuadr�cula",
        Tile: "vista de mosaicos",
        LargeIcons: "Iconos grandes",
        Layout: "Dise�o",
        SkipButton: "Omitir",
        ErrorOnFolderCreation: "Este destino ya contiene una carpeta llamada '{0}'. �Desea fusionar este contenido de la carpeta con la carpeta ya existente '{0}'?",
        InvalidFileName: "Un nombre de archivo no puede contener ninguno de los siguientes caracteres: \\/:*?\"<>|",
        GeneralError: "Por favor, vea ventana de la consola del navegador para obtener m�s informaci�n",
        ErrorPath: "FileExplorer no puede encontrar '{0}'. Revisa la ortograf�a y vuelva a intentarlo.",
        ReplaceAlert: "Archivo llamado '{0}' ya existe. Reemplazar archivo antiguo por uno nuevo?",
        DuplicateAlert: "Ya existe un archivo con el mismo nombre '{0}'. �Quieres crear el archivo con nombre duplicado",
        DuplicateFileCreation: "Ya existe un archivo con el mismo nombre en esta ubicaci�n. �Quieres cambiar el nombre de '{0}' a '{1}'?",
        DeleteFolder: " Estas seguro que quieres borrarlo ",
        DeleteMultipleFolder: "�Seguro que quieres eliminar estos {0} art�culos?",
        CancelPasteAction: "La carpeta de destino es una subcarpeta de la carpeta de origen.",
        Name: "nombre",
        Location: "ubicaci�n",
        Type: "Tipo De Art�culo",
        Created: "creado",
        Modified: "Modificado",
        DialogCloseToolTip: "cerca",
        UploadSettings: {
            buttonText: {
                upload: "Subir",
                browse: "Explorar",
                cancel: "cancelar",
                close: "cerca"
            },
            dialogText: {
                title: "Subir Box",
                name: "nombre",
                size: "tama�o",
                status: "estado"
            },
            cancelToolTip: "cancelar",
            removeToolTip: "quitar",
            retryToolTip: "Reintente",
            completedToolTip: "terminado",
            failedToolTip: "fracasado",
            closeToolTip: "cerca"
        }
    };

{% endhighlight %}

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-locale="es-ES" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://mvc.syncfusion.com/ODataServices/FileBrowser/",
        $scope.ajaxaction = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction"
    });

{% endhighlight %}

