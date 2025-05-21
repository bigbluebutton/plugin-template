# Repository of a plugin for BigBlueButton

## Description

A brief description of the plugin including a screenshot and/or a short video.

### Plugin Versioning

This repository contains the source code of a BigBlueButton plugin.

Please be aware that we have a separate branch to match each version of the SDK. This ensures that everything merged into a branch is compatible with the corresponding version of the BigBlueButton core. As of now, here's the correspondence between the branches, SDK versions, and BigBlueButton core versions:

| Repository Branch | Plugin-SDK Version | BigBlueButton Core Version |
|------------------|--------------------|----------------------------|
| v0.0.x           | v0.0.x             | v3.0.x                     |
| v0.1.x           | v0.1.x             | v3.1.x                     |

Note that this branch (`main`) does not contain any code, as it is used only for basic documentation. For more information about the plugin API features, see the documentation (`readme` files) within the specific branch you are interested in. We separate the branches because, going forward, `v0.1.x` is becoming more and more different from `v0.0.x`.

## Building the Plugin

To build the plugin for production use, follow these steps:

```bash
cd $HOME/src/plugin-template
# navigate to the correct git branch
npm ci
npm run build-bundle
```

The above command will generate the `dist` folder, containing the bundled JavaScript file named `<plugin-name>.js`. This file can be hosted on any HTTPS server along with its `manifest.json`.

If you install the Plugin separated to the manifest, remember to change the `javascriptEntrypointUrl` in the `manifest.json` to the correct endpoint.

To use the plugin in BigBlueButton, send this parameter along in create call:

```
pluginManifests=[{"url":"<your-domain>/path/to/manifest.json"}]
```

Or additionally, you can add this same configuration in the `.properties` file from `bbb-web` in `/usr/share/bbb-web/WEB-INF/classes/bigbluebutton.properties`


## Development mode

As for development mode (running this plugin from source), please, refer back to https://github.com/bigbluebutton/bigbluebutton-html-plugin-sdk section `Running the Plugin from Source`
