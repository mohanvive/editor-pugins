# Editor Plugins Guide

## Quick Start

### Prerequisites

Before getting started, make sure you have installed the [Visual Studio Code editor](https://code.visualstudio.com/download) and [Ballerina](/downloads).

>**Tip:** The VSCode Ballerina extension supports both the Ballerina Swan Lake and 1.2.x versions.

### Installing the Ballerina Extension

Follow the steps below to install the Ballerina extension.

![Installing the Ballerina Extension](/learn/images/installing-the-extension.gif)

1. Go to the <a target="_blank" href="https://marketplace.visualstudio.com/items?itemName=wso2.ballerina&ssr=false">Ballerina extension</a> in the Visual Studio Code Marketplace, and click **Install**.

2. Click **Open Visual Studio Code** and install the extension.

  >**Tip:** To verify if the extension is installed, check if the Ballerina SDK Version is displayed on the VSCode status bar. If you get `Ballerina SDK: Error` or `Ballerina SDK: Detecting` on the status bar, [enable extension debug logs](/learn/tooling-guide/visual-studio-code-extension/configurations/#debug-log) to troubleshoot.

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

    >**Tip:** If you wish to debug further, you can either use the **Debug** code lens or see [Run and Debug](/learn/tooling-guide/visual-studio-code-extension/debugging/).

5. Click the **Show Diagram** button on the editor’s title bar to view the graphical representation of the program.

## Features

### Source Code View

#### IntelliSense

##### Code completion & snippets
The extension provides you with suggestions on variables, keywords, and code snippets of language constructs (such as functions, type definitions, services, iterable constructs, etc.)

![Code Completion](/learn/images/code-completion.gif)

##### Help via Hover
When hovering over a symbol name, you will be provided with quick information about the particular symbol. For example, when hovering over a function name, you will be prompted with the associated documentation.

![Symbol Information on Hover](/learn/images/symbol-information-on-hover.gif)

When typing a function/method call expression, the signature help will show information such as the function/method call’s description and parameter information. Signature help will be triggered when typing the open parenthesis and comma.

![Signature Help](/learn/images/signature-help.gif)

#### Code Formatting
Code formatting has the two options below. 

  - Formatting a document 

  ![Formatting a Document](/learn/images/format-document.gif)

  - Formatting a selected range in the document

  ![Formatting a Document Range](/learn/images/format-document-range.gif)

#### Diagnostics
The diagnostics show you the syntax and semantic errors in the source code. Varieties of diagnostics such as errors and warnings will be shown. For a selected set of diagnostics, you can see the quick fixes. For example, the `variable assignment is required` diagnostic will have two associated quick fixes to create a new variable and ignore the return value.

![Diagnostics](/learn/images/diagnostics.gif)

#### Debugging

The VS Code Ballerina language extension comes with in-built debugging capabilities and provides the same debugging experience as the conventional VS Code Debugging.

##### Starting a Debug Session

We can start a quick debug session instantly to debug a ballerina program with `CodeLens`. We also can start a debug session with configurations
like program arguments and environment variables by adding them into the `launch.json` file.

###### Starting a Program Debug Session

Ballerina extension provides multiple options to debug your Ballerina program and the easiest way will be using our context-aware `Debug` CodeLens support provided by the extension.
The extension can detect any program entry points (main function/service definition) on the fly, and the CodeLens will appear automatically.  

Follow the steps below to start a quick debug session.

![Start_Main Quick Debug Session](/learn/images/start-quick-main-debug-session.gif)

<br/>

1. Open the folder, which includes the Ballerina program you want to debug, and open the source file in the editor.

2. Add the debug points you require by clicking in front of the line numbers of the file you want to debug.

3. Click the `Debug` CodeLens which is just above the `main()` method.

###### Starting a Test Debug Session

The Ballerina test functions can also be debugged using the codelens. The `debug` codelens will automatically appear on top of each Ballerina test function and the users are able to execute/debug only a selected test case by clicking on the corresponding codelens, as shown below.

![Start_Test Quick Debug Session](/learn/images/start-quick-test-debug-session.gif)

<br/>

###### Debug Session with Configurations

Follow the steps below to start a debug session with configurations. All the configurations need to be added in the `launch.json` file.

![Start Debug Session](/learn/images/start-debug-session.gif)

<br/>

1. Open the folder, which includes the Ballerina program you want to debug, and select the file.

2. Press the **Control + Shift + D** keys (for Mac: **Command + Shift +D**) to launch the Debugger view.

3. Click **create a launch.json** file and then select **Ballerina Debug** as the **Environment**.

    You view the opened `launch.json` file. 

4. Add/edit the relevant configurations for debugging in the `launch.json` file.

5. Add the debug points you require by clicking in front of the line numbers of the file you want to debug.

Then, you can start a program, test, or remote debug session as shown below.

>**Info:** If you launch the debug session through VS Code, the working directory will be the Ballerina package root. However, you can use remote debugging for alternative working directories.

<br/>

####### Starting a Program Debug Session

Follow the steps below to start a program debug session.

1. Select **Ballerina Debug** from the drop-down available in the upper left corner to start a program debugging session.

2. Click the **Start Debugging** icon on the upper left corner to start debugging.

    You view the output in the **DEBUG CONSOLE**.

    ![Program Debug](/learn/images/program-debug.gif)

<br/>

####### Starting a Test Debug Session

Follow the steps below to start a test debug session.

1. Select **Ballerina Test** from the drop-down available in the upper left corner to start a test debugging session.

2. Click the **Start Debugging** icon on the upper left corner to start debugging.

    You view the output in the **DEBUG CONSOLE**.

    ![Test Debug](/learn/images/test-debug.gif)

<br/>

###### Starting a Remote Debug Session

Follow the steps below to start a remote debug session.

1. Create the `launch.json` file to add debug configurations if it is not created already. Refer [Debug Session with Configurations](#debug-session-with-configurations) section on how to create the `launch.json` file.

2. Add relevant `debuggeeHost` and `debuggeePort` under `Ballerina Remote` configurations section in the `launch.json` file.

3. After setting the remote debug configurations, select **Ballerina Remote** from the drop-down available in the upper left corner to start a remote debugging session.

4. Open the Terminal and execute the Ballerina command, which you want to debug, out of the supported remote debugging commands below. 

    - Debugging a Ballerina package or a single file: 

    ```bash
    bal run --debug <DEBUGGEE_PORT> <BAL_FILE_PATH/PACKAGE_PATH>
    ```

   - Debugging Ballerina executable JAR:  

    ```bash 
    bal run --debug <DEBUGGEE_PORT> <EXECUTABLE_JAR_FILE_PATH>
    ```

    - Debugging Ballerina tests: 

    ```bash
    bal test --debug <DEBUGGEE_PORT> <PACKAGE_PATH>
    ```
    
    The terminal will show the following log:

    ```bash
    Listening for transport dt_socket at address: 5005
    ```

5. Click the **Start Debugging** icon on the upper left corner to start debugging.

    You view the output in the **DEBUG CONSOLE**.

    ![Remote Debug](/learn/images/remote-debug.gif)

<br/>

##### Using the Debugging Features

The following debugging features are supported by Ballerina.

- Launch/Attach
- Breakpoints
  - Conditional Breakpoints
  - Logpoints
- Pause & Continue
- Step In/Out/Over
- Variables
- Call Stacks
- Strands
- Expression Evaluation

>**Info:** For more information on debugging features using VS Code, go to the [VS Code Documentation](https://code.visualstudio.com/docs/editor/debugging).

##### Debug Configurations

Ballerina debugger supports various debug configuration options via `launch.json` file. You can either add configurations to the existing `launch.json` file (which is located in your workspace root under the `.vscode` directory), or you can generate `launch.json` configurations file with default values by,

1. Click the **Run and Debug** icon in the left menu or press the **Control + Shift + D** keys, to launch the Debugger view. (for Mac - **Command + Shift +D**).

2. Click on **create a launch.json file** and then select **Ballerina Debug**.

![Run And Debug](/learn/images/run-and-debug.png)

<br/>

![Ballerina Debug](/learn/images/ballerina-debug.png)

<br/>

Here are the default configurations generated for the Ballerina debugging:

![Debug Configurations](/learn/images/debug-configurations.png)

<br/>

>**Info:** You can debug a Ballerina program without generating the `launch.json` configurations file, but it is not possible to manage launch configurations and set up advanced debugging.

###### Ballerina launch.json attributes

The auto-generated `launch.json` file consists of three main configurations, namely, `Ballerina Debug`, `Ballerina Test`, and `Ballerina Remote`. Each configuration supports different attributes, and those attributes can be identified with the help of IntelliSense suggestions (`⌃Space`).

The following attributes are mandatory for all configurations.

- `name` - The reader-friendly name to appear in the Debug launch configuration dropdown.
- `type` - The type of debugger to use for this launch configuration. The attribute value must be kept as `ballerina` for all Ballerina debugging configuration types.
- `request` - The request type of this launch configuration. Currently, launch and attach are supported.

The following attributes are supported for all Ballerina `launch` configurations.

- `programArgs` - Any program arguments that are required to be passed into the `main` function of the Ballerina program to be launched, can be passed as a list of strings.
- `commandOptions` - If required, you can configure command options for the Ballerina program to be launched, as a list of strings. You can see the list of all the available command options by executing the following CLI commands in your terminal.
    - For `Ballerina Debug` configuration:

    ```bash
    bal run --help
    ```

    - For `Ballerina Test` configuration:

    ```bash
    bal test --help
    ```

- `env` - Any environment variables you need to configure for the launching Ballerina program can be passed as a map of strings (name and value).
- `debugTests` - Indicates whether to debug the tests for the given script.

The following attributes are supported for all Ballerina `attach` configurations.

- `debuggeeHost` - Host address of the remote process to be attached (If not specified, the default value will be the localhost(`127.0.0.1`)).
- `debuggeePort` - Port number of the remote process to be attached.


#### Code Navigation

##### Go to Definition 

For a symbol, this feature will navigate you to the definition of the particular symbol. For example, when invoking the go to definition from a function call expression, you will be navigated to the definition of the function. Apart from jumping to the definition, the peek definition will also be supported. The behavior will be the same not only for the constructs within the sources in the current package but also for external modules and standard libraries as well.

![Go to Definition](/learn/images/go-to-definition.gif)

##### Find all References

Invoking the references on a symbol will prompt you with all the symbol references in the current package.

![Find all References](/learn/images/find-all-references.gif)

#### Rename Symbols
This feature allows you to rename symbols by renaming all the references of the particular symbol.

![Rename Symbols](/learn/images/rename-symbols.gif)

#### Code Actions
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

#### Code Lens
##### Documentation Code Lens

The `Document This` code lens is shown for the public functions without documentation. 

![Documentation Code Lens](/learn/images/documentation-code-lens.gif)

##### Run and Debug Code Lenses

Run and debug code lenses are shown for the entry points of the Ballerina project and for its test cases. The entry points include the main function and the services within the default module of the project.

![Run and Debug Code Lenses](/learn/images/run-and-debug-code-lenses.gif)

#### Commands
- **Show Examples**: It lists the available examples of the Ballerina language. By clicking on each example, you can explore each source code. 
- **Build**: It is a quick access to build your Ballerina project. Once executed, the current Ballerina project relative to the currently-opened text editor is built using the `bal build` CLI command.
- **Run**: It runs your Ballerina project. Once executed, the opened Ballerina project is built using the `bal run` CLI command.
- **Test**: It runs all the tests in your Ballerina project using the `bal test` CLI command.
- **Build Documentation**: It is a quick guide to generate documentation for your Ballerina project. Once executed, the documentation is generated using the `bal doc` CLI command. The generated documentation can be found inside the `apidocs` directory in the project `target`.
- **Show Diagram**: It is a palette reference to access the **Diagrams**. On execution, the diagram editor of the first diagram component listed under the **Diagrams** view is rendered.
- **Add Module**: It adds a [Ballerina module](/learn/user-guide/ballerina-packages/modules/) for the given module name using the `bal add` CLI command.  
- **Create 'Cloud.toml'**: It generates a `Cloud.toml` file for your Ballerina project according to the default [cloud specifications](https://github.com/ballerina-platform/ballerina-spec/blob/master/c2c/code-to-cloud-spec.md).
- **Paste JSON as Record**: This command converts a JSON string (that is copied to the clipboard) to a Ballerina record(s) and pastes it in your code.

### Low Code View




## Configuration



## Frequently Asked Questions
