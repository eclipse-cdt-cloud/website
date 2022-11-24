+++
fragment = "content"
weight = 20

title = "Eclipse Theia: Development Tool Platform"

[sidebar]
  sticky = true
+++

For creating a specialized C/C++ tool or custom IDE, it is typically most efficient to build on an existing tool platform, which already provides generic tool features, such as a file explorer, editors with rich language-editing support, menus, user interfaces for process output or debugging, etc.
To meet the specific requirements of your particular tool or IDE, you then extend and customize this generic platform with specific extensions.

<p align="center" style="padding-top: 1em; padding-bottom: 1em">
  <img src="/images/cdtcloud-screenshot.png" width="85%" style="border-radius: 5px" />
</p>

As you usually want to have full control over every aspect of your custom tool, [Eclipse Theia™](https://theia-ide.org) is a popular choice for a tool platform in general, and for custom C/C++ development in particular.
Theia is an extensible and very flexible, vendor neutral open-source IDE platform to develop full-fledged multi-language Cloud & Desktop IDE-like products with state-of-the-art web technologies.

### Getting started with Theia

To learn more about Theia, please visit the [Theia webpage](https://theia-ide.org) and browse through its [getting started guide](https://theia-ide.org/docs/getting_started).
This will give you a solid overview about Theia's architecture and main concepts.

For your custom C/C++ tool, we recommend to start off from the [CDT.cloud Blueprint]({{< relref  "blueprint" >}}) and use it as a template.
CDT.cloud Blueprint is a Theia-based application which already contains a collection of extensions and configurations that likely apply to your C/C++ tool use case.
Thus, all documentation on Theia applies to CDT.cloud Blueprint as well, but it already adds components and best practices that typically are useful for C/C++ tools.

To learn more about composing Theia-based applications in general, please refer to the [Theia documentation](https://theia-ide.org/docs/composing_applications).

### Extending Theia applications

Theia provides typical tool features out of the box, but can be extended and customized in virtually all aspects to eventually provide a streamlined tool offering for your specific purpose.
Therefore, Theia provides two main extension mechanisms: VS Code extensions and Theia extensions.

By pulling in *VS Code extensions*, you can benefit from the vast ecosystem of tool capabilities available for VS Code.
In the context of C/C++ tools, popular extensions include [vscode-clangd](https://open-vsx.org/extension/llvm-vs-code-extensions/vscode-clangd) for C/C++ language editing support, [GDB debug adapters](https://open-vsx.org/extension/eclipse-cdt/cdt-gdb-vscode), [CodeChecker](https://open-vsx.org/extension/codechecker/codechecker), etc.

*Theia extensions*, on the other hand, are more powerful than VS Code extensions and allow you to deeply customize all aspects of the tool platform, including the workbench structure, e.g. by adding a global toolbar, removing user interface components that you don't need in your particular tool, adding wizards in the frontend and providing custom backend services.

For an overview, please read more about the [Theia extension mechanisms](https://theia-ide.org/docs/extensions) and follow the guides on [integrating VS Code extensions](https://theia-ide.org/docs/authoring_vscode_extensions) and [developing Theia extensions](https://theia-ide.org/docs/authoring_extensions).

### Packaging Theia applications

When you want to package your custom tool as a desktop application, you'll need to build your entire application for the operating systems you aim to support and likely want to integrate an update mechanism and add branding, such as application icons, etc.
To learn more about dealing with those tasks, please consult the [Theia packaging documentation](https://theia-ide.org/docs/blueprint_documentation).
You can also check the CDT.cloud Blueprint for a concrete implementation.
