+++
fragment = "content"
weight = 30

title = "CDT.cloud Blueprint"

[sidebar]
  sticky = true
+++

CDT.cloud Blueprint is a template tool for building custom, web-based C/C++ tools.
It is based on the [Theia development tool platform]({{< relref  "tool-platform" >}}) and integrates several existing open source components to provide a starting point for building a custom C/C++ IDE.
This includes C/C++ language features, debugging support, a memory inspector, and a tracing view.

The purpose of CDT.cloud Blueprint is two-fold:

1. You can download and run it to try out several CDT.cloud components (see [download page](/#blueprint))
2. You can use it as a template to start off your custom C/C++ tool (see instructions below)

<p align="center" style="padding-top: 1em; padding-bottom: 1em">
  <img src="/images/diagramanimated.gif" width="70%" style="border-radius: 5px" />
</p>

### Building and running

The sources including build instructions are available on the [CDT.cloud Blueprint Github repository](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint).
Please follow the instructions on the [Github readme](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/README.md) to build and run CDT.cloud Blueprint as a desktop app, browser app, or in Docker.

It includes several C/C++ extensions to provide language support and debug support.
For a complete list of the used Theia extensions and VS Code extensions, please refer to the [application's `package.json`](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/applications/electron/package.json).

### Welcome page

To greet and guide users on initial start-up of CDT.cloud Blueprint, it provides a welcome page.
The welcome page is essentially a web page in a Theia view that provides general information, but also links to relevant web resources.
Users can also trigger commands directly from the welcome page, such as opening folders, settings, as well as [creating example projects](#example-project-generator).

The welcome page is contributed to the product in the [TheiaBlueprintGettingStartedContribution](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/theia-extensions/theia-blueprint-product/src/browser/theia-blueprint-getting-started-contribution.ts).

### Example project generator

CDT.cloud Blueprint contains an example generator which allows users to create pre-defined projects based on a project template.
Projects can either be generated from the welcome page or via the command *Generate CDT.cloud Blueprint Example*.
Once a project is generated, a defined file -- such as a readme -- of this project is opened for the user.
The generator is implemented by the Theia extension [`blueprint-example-generator`](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/theia-extensions/blueprint-example-generator).

The list of project types can be easily extended to add more project templates with the following steps:

1. Add the project template to the folder [`resources`](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/tree/master/theia-extensions/blueprint-example-generator/resources)
2. Add the project template name to the list of projects in the [command contribution](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/theia-extensions/blueprint-example-generator/src/browser/example-generator-contribution.ts)
3. Optionally specify the file to be opened after generation in the [`ExampleGeneratorServiceImpl`](https://github.com/eclipse-cdt-cloud/cdt-cloud-blueprint/blob/master/theia-extensions/blueprint-example-generator/src/node/example-generator-service.ts)
