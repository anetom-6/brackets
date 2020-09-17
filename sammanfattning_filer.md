# base-config

# commands
Håller koll på kommandon och meny.
- [CommandManager.js](src/command/CommandManager.js)
  * Manages global application commands that can be called from menu items, key bindings, or subparts of the application.
- [Commands.js](src/command/Commands.js)
  * Listar alla möjlig kommandon.
- [DefaultMenus.js](src/command/DefaultMenus.js)
  * Skapar strandard menyn för brackets
- [KeyBindingManager.js](src/command/KeyBindingManager.js)
  * Håller koll på mappningen av alla kommandon. (Filnamet)
- [Menus.js](src/command/Menus.js)
  * Skapar också en meny?

# document
Gör de faktiska ändringarna i dokumenten och håller koll på om de har ändrats eller inte.
- [ChangedDocumentTracker.js](src/document/ChangedDocumentTracker.js)
  * Håller koll på om filerna har ändrats. Verkar anta att alla filer har ändrats om fönstret lämnar fokus.
- [Document.js](src/document/Document.js)
  * Håller koll på hur en fil har ändrats. Change, delete, flyuttningar av text mm.
- [DocumentCommandHandlers.js](src/document/DocumentCommandHandlers.js)
  * Håller kommandon för att stänga, öppna, spara filer mm.
- [DocumentManager.js](src/document/DocumentManager.js)
  * Här händer det jucie stuff. Kolla på kommentarerna. Men verkar som all ändring av filerna händer. Kommunicerar mycket med EditorManager.js
- [InMemoryFile.js](src/document/InMemoryFile.js)
  * Håller filer som inte existerar på hårdisken.
- [TextRange.js](src/document/TextRange.js)
  * Håller koll på vilka rader text har ändras. Men kan hamna "out of sync" om filen ändras på oväntat sätt.

# Editor
Verkar vara UI för Editorfönster. Alltså visar vilka filer man ändrar och hur de ska displayas.
- [CodeHintList.js](src/editor/CodeHintList.js)
  * Visar en lista på "hints"-alternativ i editorn när du skriver kod.
- [CodeHintList.js](src/editor/CodeHintList.js)
  * Räknar ut vilka "hints" som användaren kan vara intresserad av berodende på språk mm.
- [CSSInlineEditor.js](src/editor/CSSInlineEditor.js)
  * Verkar leta upp relevanta "selectors" (vad nu det är) för attribute och taggar beroende på vilken posistion 
   man är på. Lite oklart vad den gör(tycker jag). Men det är för CSS
- [Editor.js](src/editor/Editor.js)
  * Dispateches events. Lyssnar på olika event från piltangenterna och musen samt "lostContent", "opitonChange", och "beforeDestroy"
- [EditorCommandHandlers.js](src/editor/EditorCommandHandlers.js)
  * Sickar kommandon som påverkar den editorn som är i fokus.
- [EditorManager.js](src/editor/EditorManager.js)
  * Ansvarar för UI för en editor. "This **ESSENTIALLY** mirrors the 'current document' property maintained by DocumentManager's model." Pratar jättemycket med DocumentMangaer.js. Verkar också vara rätt jucie.
- [EditorOptionHandlers.js](src/editor/EditorOptionHandlers.js)
  * Verkar hämta Options inställningar till editorn.
- [EditorStatusBar.js](src/editor/EditorStatusBar.js)
  * Updatterar delar av "status bar" efter editorns tillstånd.
- [ImageViewer.js](src/editor/ImageViewer.js)
  * Visar bilder?
- [InlineTextEditor.js](src/editor/InlineTextEditor.js)
  * Ska mergas in i MultiRangeInlineEditor.js. Så gör typ samma sak.
- [InlineWidget.js](src/editor/InlineWidget.js)
  * Hanterar visningen av widgets?
- [MultiRangeInlineEditor.js](src/editor/MultiRangeInlineEditor.js)
  * Visar en inline editor för att redigera flera text ranges. Läs kommentarerna i filen.

# Extensibility
Hanterar extensions.

- [ExtensionManager.js](src/extensibility/ExtensionManager.js)
  * Håller koll på de installerade extensions.
- [ExtensionManagerDialog.js](src/extensibility/ExtensionManagerDialog.js)
  * Visar information om extension och installationer av dem.
- [ExtensionManagerView.js](src/extensibility/ExtensionManagerView.js)
  * UI för hanteringen av extensions?
- [ExtensionManagerViewModel.js](src/extensibility/ExtensionManagerViewModel.js)
  * Viar också extensions?
- [InstallExtensionDialog.js](src/extensibility/InstallExtensionDialog.js)
  * Dialogruta för installation av en extension?
- [Package.js](src/extensibility/Package.js)
  * Functions for working with extension packages
- [registry_utils.js](src/extensibility/registry_utils.js)
  * Se fil. Verkar vara någon nödlösning.

## Node
- [node/Readme.md](src/extensibility/node/README.md):
> ## Brackets Extensibility
>
>This code is used by Brackets to implement its extension management features. It is likely not useful to anyone not >working with Brackets extensions.
- [node/ExtensionManagerDomain.js](src/extensibility/node/ExtensionManagerDomain.js)
  * Hanterar installationen av en extension?
- [node/npm-installer.js](src/extensibility/node/npm-installer.js)
  * Private function to run "npm install --production" command in the extension directory.
- [node/package-validator.js](src/extensibility/node/package-validator.js)
  * Validerar ett paket(Extension?)
### Spec

- [node/spec/Installation.spec.js](src/extensibility/node/spec/Installation.spec.js)
  * Här verkar själva installationen ske.
- [node/spec/Validation.spec.js](src/extensibility/node/spec/Validation.spec.js)
  * Validerar en installation?

# Extensions
Extensions som kommer installerade i brackets. Kommer inte gå igenom alla dom.
## Default
- [deafault/README.md](src/extensions/default/README.md)
## Dev
- [dev/README.md](src/extensions/dev/README.md)
## Samples
- [samples/README.md](src/extensions/samples/README.md)

# Features
- [FindReferencesManager.js](src/features/FindReferencesManager.js)
  * Hittar referenser i editorn?
- [JumpToDefManager.js](src/features/JumpToDefManager.js)
  * Hoppar till rätt ställe? Alltså där referensen fanns?
- [ParameterHintsManager.js](src/features/ParameterHintsManager.js)
  * Hanterar hints i editorn? Alltså förslag som ska visas?
- [PriorityBasedRegistration.js](src/features/PriorityBasedRegistration.js)
  * Verkar prioritera olika hints som och bestämer vilken som ska visas.

# File
- [FileUtils.js](src/file/FileUtils.js)
  * Set of utilities for working with files and text content.

# Filesystem
- [Directory.js](src/filesystem/Directory.js)
  * Verkar hålla data för andra filer.
- [File.js](src/filesystem/File.js)
  * Verkar också hålla infromation för andra filer.
- [FileIndex.js](src/filesystem/FileIndex.js)
  * Håller data för FileSystem.js
- [FileSystem.js](src/filesystem/FileSystem.js)
  * Håller en reperentasiton av alla filer. Mer info finns på [wikin](https://github.com/adobe/brackets/wiki/File-System-Implementations).
- [FileSystemEntery.js](src/filesystem/FileSystemEntry.js)
  * Lägger till nya filer i systemet.
- [FileSystemError.js](src/filesystem/FileSystemError.js)
  * Hanterar alla errors som kan uppstå.
- [FileSystemStats.js](src/filesystem/FileSystemStats.js)
  * Håller all information om en fil. Som hur stor den är, när den skapades mm.
- [WatchedRoot.js](src/filesystem/WatchedRoot.js)
  * 
  
# Samples 
- [Getting started](smaples)
  * Hanledning hur man kommer igång på flera olika språk
  
# Tasks
- [common.js](tasks/lib/common.js)
  * Tar reda på om det är Windows, Mac eller Linux oxh skapar sedan en JSON-fil där den infon lagras
- [build.js](tasks/build.js)
  * Ser ut att jämföra den lokala head-filen med de på GIT och letar om branchnamnet existerar. Checkar sedan om om filen är CLA-registrerad. Om inte, blir den     nekad. I korta drag ser den ut att titta om allt är enligt standard innan man får ladda upp den.
- [CLA-exception]
  * Antar att den inte checkar om CLA existerar på de användarna i listan
- [npm-install.js](tasks/npm-install.js)
  * Hämtar och installerar Node package manager, samt extensions till det
- [pack-web-dependencies.js](tasks/pack-web-dependencies.js)
  * Använder Webpack (https://webpack.js.org/) på saker som används i webläsaren, så som node modules
- [test.js](tasks/test.js)
  * Används för testning av mjukvaran. Kräver att Grunt, child_process, q, child_process_exec och xmldc
- [update-release-number.js](tasks/update-release-number.js)
  * Kräver Grunt och semver. Uppdaterar versionsnumret i JSON-filen
- [write-config.js](write-config.js)
  * Kräver Grunt från /build och /lib.common. Sätter ihop jason från package och src/brackets.config för att sedan skriva till src/config.json
  
# Tools
 -[setup_for_hacking.bat]
 * Ändrar bracket src till developer src, för testing av developer bracket

 -[restore_installed_build.bat/.sh]
 * Återställer ändringar som set_up_for_hacing gjorde
 
 # Tools
 - [restore_installed_build.bat](tools/restore_installed_build.bat)
  * Används när man vill använda Brackets som vanligt istället för i developer mode
  
 - [restore_installed_build.sh](tools/restore_installed_build.sh)
  * Används när man vill använda Brackets som vanligt istället för i developer mode
  
 - [setup_for_hacking.bat](tools/setup_for_hacking.bat)
  * Används för att ställa in i "developer mode"
 
 - [setup_for_hacking.sh](tools/setup_for_hacking.sh)
  * Används för att ställa in i "developer mode"

 - [setup_server_smokes.bat](tools/setup_server_smokes.bat)
  * Används för att starta en lokal server för att komma åt Brackets server smoke test fil från GitHub
  
 - [setup_server_smokes.sh](tools/setup_server_smokes.sh)
  * Används för att starta en lokal server för att komma åt Brackets server smoke test fil från GitHub
