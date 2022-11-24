+++
fragment = "content"
weight = 20

title = "Development Tool Platform"

[sidebar]
  sticky = true
+++

For creating a specialized C/C++ tool or custom IDE, it is typically most efficient to build on an existing tool platform, which already provides generic tool features, such as a file explorer, editors with rich language-editing support, menus, user interfaces for process output or debugging, etc.
To meet the specific requirements of your particular tool or IDE, you then extend and customize this generic platform with specific extensions.

<p align="center" style="padding-top: 1em; padding-bottom: 1em">
  <img src="/images/cdtcloud-screenshot.png" width="85%" style="border-radius: 5px" />
</p>

The two most popular choices for a modern tool platform are [VS Code](https://code.visualstudio.com) and [Eclipse Theia](https://theia-ide.org).
VS Code is a code editor by Microsoft, which can be extended by using an [extension API](https://code.visualstudio.com/api).
Theia, on the other hand, is an extensible and very flexible, vendor neutral open-source IDE platform to develop full-fledged multi-language Cloud & Desktop IDE-like products. Theia not only supports VS Code extensions, but also provides an even more [powerful extension mechanism](https://theia-ide.org/docs/extensions) that allows you to take control over every aspect of your tool.

Whether to use one or the other for a specific tool project depends on [various factors](https://eclipsesource.com/de/blogs/2019/12/06/the-eclipse-theia-ide-vs-vs-code).
In a nutshell, if you rather want to provide an extension to an existing code editor rather than creating an own product, VS Code may be a good choice for your project.
If you want, however, to provide a white-labeled, tailored product for your customers or your own developers and you need to be able to take control over several aspects of your tool, you might be better served with Eclipse Theia.

As the decision on VS Code vs Eclipse Theia depends on the respective tool project, many of the CDT.cloud components are actually shipped as VS Code extensions.
This way, they can be used either way, whether you use VS Code or Eclipse Theia.

With custom C/C++ development tools, however, you often need to have full control over every aspect of your custom tool, which makes Theia is a popular choice in this context.
Thus, we point you to the right resources to get started with Theia below.

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
