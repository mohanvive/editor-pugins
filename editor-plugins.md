# The Ballerina Extension for Visual Studio Code

The Visual Studio Code Ballerina extension provides a set of rich language features along with an enhanced user experience. 
It offers easy development, execution, debugging, and testing for the Ballerina programming language. 
The Ballerina language possesses a bidirectional mapping between its syntaxes and the visual representation. 
You can further visualize the graphical representation of your Ballerina source via the extension.

---
## Quick Start

### Prerequisites

Before getting started, make sure you have installed the [Visual Studio Code editor](https://code.visualstudio.com/download).

>**Tip:** The VSCode Ballerina extension supports both the Ballerina Swan Lake and 1.2.x versions.

### Installing the Ballerina Extension

Follow the steps below to install the Ballerina extension.

1. [Download](https://ballerina.io/downloads/) and [install](https://ballerina.io/learn/user-guide/getting-started/setting-up-ballerina/#installing-ballerina) Ballerina.
2. [Install](https://ballerina.io/learn/tooling-guide/visual-studio-code-extension/quick-start/#installing-the-ballerina-extension) Ballerina VS Code Extension. Launch VS Code Quick Open (`Ctrl + P`), and paste following `ext install WSO2.ballerina`
3. Open a Ballerina `.bal` file or a package directory to activate the extension.

	**Info:** When the extension is activated, you can see the `Ballerina SDK: <version>` in the status bar at the bottom left corner.

    ![Diagrams View](/learn/images/show-version-on-vscode.png)

### Running Your First Ballerina Program

Follow the steps below to create a sample Ballerina program in VSCode.

![Running Your First Ballerina Program](/learn/images/running-your-program.gif)

1. Click **View** in the menu bar of the editor, and click **Command Palette**.

    >**Tip:** You can use the shortcut methods `⌘ + ↑ + P` on Mac and `Ctrl + Shift + P` on Windows and Linux.

2. In the search bar, type `Ballerina Examples` and click **Ballerina: Show Examples**.

3. Select the **Hello World Main** example.

4. Click on the **Run** code lens on the editor. 

    You just ran your first Ballerina program with a few clicks.

    >**Tip:** If you wish to debug further, you can either use the **Debug** code lens or see [Run and Debug](#debugging).

5. Click the **Show Diagram** button on the editor’s title bar to view the graphical representation of the program.

## Functionalities

### Source Code View

<details open>
<summary>IntelliSense</summary>

##### Code completion & snippets
The extension provides you with suggestions on variables, keywords, and code snippets of language constructs (such as functions, type definitions, services, iterable constructs, etc.)

![Code Completion](/learn/images/code-completion.gif)

##### Help via Hover
When hovering over a symbol name, you will be provided with quick information about the particular symbol. For example, when hovering over a function name, you will be prompted with the associated documentation.

![Symbol Information on Hover](/learn/images/symbol-information-on-hover.gif)

When typing a function/method call expression, the signature help will show information such as the function/method call’s description and parameter information. Signature help will be triggered when typing the open parenthesis and comma.

![Signature Help](/learn/images/signature-help.gif)
</details>

<details>
<summary>Code Formatting</summary>
Code formatting has the two options below. 

  - Formatting a document 

  ![Formatting a Document](/learn/images/format-document.gif)

  - Formatting a selected range in the document

  ![Formatting a Document Range](/learn/images/format-document-range.gif)
</details>

<details>
<summary>Diagnostics</summary>

The diagnostics show you the syntax and semantic errors in the source code. Varieties of diagnostics such as errors and warnings will be shown. For a selected set of diagnostics, you can see the quick fixes. For example, the `variable assignment is required` diagnostic will have two associated quick fixes to create a new variable and ignore the return value.

![Diagnostics](/learn/images/diagnostics.gif)

</details>

<details>
<summary>Debugging</summary>


</details>

<details>
<summary>Code Navigation</summary>

##### Go to Definition 

For a symbol, this feature will navigate you to the definition of the particular symbol. For example, when invoking the go to definition from a function call expression, you will be navigated to the definition of the function. Apart from jumping to the definition, the peek definition will also be supported. The behavior will be the same not only for the constructs within the sources in the current package but also for external modules and standard libraries as well.

![Go to Definition](/learn/images/go-to-definition.gif)

##### Find all References

Invoking the references on a symbol will prompt you with all the symbol references in the current package.

![Find all References](/learn/images/find-all-references.gif)

#### Rename Symbols
This feature allows you to rename symbols by renaming all the references of the particular symbol.

![Rename Symbols](/learn/images/rename-symbols.gif)

</details>

<details>
<summary>Code Actions</summary>

There are two types of code actions suggested based on the node at a given cursor position and based on the diagnostic at a given cursor position.

![Create Variable](/learn/images/create-variable.gif)
![Document This](/learn/images/document-this.gif)

##### Create Variable Code Actions
Below demonstrate the types of code actions available for creating a variable.
- `Create variable`: Create a variable for an expression where the `Variable Assignment Required` diagnostic is present.
- `Create variable and type guard`: Create a type guard to handle the error gracefully when the `Variable assignment Required` diagnostic is present.
- `Create variable and check error`: Add a check expression when the `Variable assignment Required` diagnostic is present.
- `Ignore return value`: Ignore the return value with the `_` where the `Variable Assignment Required` diagnostic is present.

##### Code Actions for Union Types
Below demonstrate the code actions available for union type variables.
- `Type guard variable`: Type guard a variable, if the variable is of the union type.
- `Add check error`: When there is an error union, add a check statement.

##### Code Actions for Imports
Below demonstrate the code actions available for imports.
- `Import a module`: Add the import statement for a module, which has a reference without an import statement. This supports only the language library and the standard library.
- `Optimize imports`: Optimize the import statements to remove unused imports and arrange the imports in alphabetical order.

##### Code Actions for Documentation
Below demonstrate the code actions available for documentation.
- `Document this`: Add the documentation to the top-level constructs, resources, and methods.
- `Document all`: Document all the top-level constructs.
- `Update documentation`: Update the existing documentation when parameters are missing or not documented. This depends on the warning diagnostic sent by the compiler.

##### Code Actions for Incompatible Types
Below demonstrate the code actions available for incompatible types.
- `Change variable type`: Changes the type of a variable.
- `Add type cast`: Add a type cast for the incompatible types. 
- `Fix return type`: Changes the incompatible return type.
- `Change parameter type`: Changes the type of a function/ method parameter.

##### Code Actions for Create Functions 
Below demonstrate the code actions available for creating functions.
- `Create a function`: Creates a function using the selected variables/parameters.
- `Implement a method`: Implements the selected method.

</details>

<details>
<summary>Code Lens</summary>

##### Documentation Code Lens

The `Document This` code lens is shown for the public functions without the documentation. 

![Documentation Code Lens](/learn/images/documentation-code-lens.gif)

##### Run and Debug Code Lenses

Run and debug code lenses are shown for the entry points of the Ballerina project and for its test cases. The entry points include the main function and the services within the default module of the project.

![Run and Debug Code Lenses](/learn/images/run-and-debug-code-lenses.gif)

</details>

<details>
<summary>Commands</summary>

#### Commands
- **Show Examples**: It lists the available examples of the Ballerina language. By clicking on each example, you can explore each source code. 
- **Build**: It is a quick access to build your Ballerina project. Once executed, the current Ballerina project relative to the currently-opened text editor is built using the `bal build` CLI command.
- **Run**: It runs your Ballerina project. Once executed, the opened Ballerina project is built using the `bal run` CLI command.
- **Test**: It runs all the tests in your Ballerina project using the `bal test` CLI command.
- **Build Documentation**: It is a quick guide to generate documentation for your Ballerina project. Once executed, the documentation is generated using the `bal doc` CLI command. The generated documentation can be found inside the `apidocs` directory in the project `target`.
- **Show Diagram**: It is a palette reference to access the **Diagrams**. On execution, the diagram editor of the first diagram component listed under the **Diagrams** view is rendered.
- **Add Module**: It adds a [Ballerina module](https://ballerina.io/learn/organizing-ballerina-code/modules/) for the given module name using the `bal add` CLI command.  
- **Create 'Cloud.toml'**: It generates a `Cloud.toml` file for your Ballerina project according to the default [cloud specifications](https://github.com/ballerina-platform/ballerina-spec/blob/master/c2c/code-to-cloud-spec.md).
- **Paste JSON as Record**: This command converts a JSON string (that is copied to the clipboard) to a Ballerina record(s) and pastes it in your code.

</details>

### Low Code View

![Low Code View - Diagram View](/learn/images/low-code-view.gif)

## Configuration
- **Code Lens - All: Enabled** : It enables all code lens features irrespective of the **Code Lens - Docs: Enabled** and **Code Lens - Executor: Enabled** settings and is enabled by default.
- **Code Lens - Docs: Enabled** : It enables the **Documentation** [code lens](#documentation-code-lens) feature, which provides Ballerina document generation capabilities and is enabled by default. This configuration is overridden by the **Code Lens - All: Enabled** settings.
- **Code Lens - Executor: Enabled** : It enables the **Executor** [code lens](#run-and-debug-code-lenses) feature, which provides quick run and debug capabilities for the Ballerina language. It is enabled by default. This configuration is overridden by the **Code Lens - All: Enabled** settings.
- **Data Mapper: Url** : It specifies the URL of the [data mapping](/learn/tooling-guide/visual-studio-code-extension/language-support/#data-mapping) service backend.
- **Debug Log** : It enables printing debug messages on to the Ballerina output channel and is disabled by default. These debug logs mainly include additional logs added for troubleshooting the extension.
- **Enable File Watcher** : It enables watching file change events of the Ballerina project and is enabled by default.
- **Ballerina: Enable Performance Forecast** :
- **Ballerina: Enable Semantic Highlighting** : 
- **Enable Telemetry** : It enables the Ballerina [telemetry](https://code.visualstudio.com/docs/getstarted/telemetry) service and is enabled by default. 
- **Home** - It specifies the Ballerina home directory path and is only applicable if the **Plugin - Dev: Mod** is enabled.
- **Ballerina: Low Code Mode** : 
- **Ballerina: Plugin Dev Mode** : It enables the plugin development mode and is disabled by default. If it is disabled, the extension picks up the Ballerina runtime installed in the environment. Also, if it is enabled, the extension picks up the Ballerina runtime defined in the **Home** [configuration](/learn/tooling-guide/visual-studio-code-extension/configurations/#home).
- **Ballerina: Trace Log** : It enables printing trace messages onto the Ballerina output channel and is disabled by default. These trace logs mainly include the details of the requests sent from the extension to the Ballerina Language Server.

## Frequently Asked Questions
