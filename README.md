# Fulltime Force Plugin

<table width='100%' align="center">
    <tr>
        <td align='left' width='100%' colspan='2'>
            WordPress plugin that scan this repository and shows commit history
        </td>
    </tr>
</table>

Based on the following boilerplate by <a href="https://github.com/brandonkramer/wordpress-plugin-boilerplate">Brandon Krammer</a><br><br>
Should be run inside your plugins folder (wp-content/plugins).

```bash {"id":"01HW937V1YM5NZJFYWGJXC402A"}
npx wp-strap plugin
```

## Requirements

- [Composer](https://getcomposer.org/doc/00-intro.md)
- [Node.js](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

## File structure

You can add your own new class files by naming them correctly and putting the files in the most appropriate location,
see other files for examples. Composer's Autoloader and the Bootstrap class will auto include your file and instantiate
the class. The idea of this organisation is to be more conscious of structuring your code.

```bash {"id":"01HW937V1Z4SXJKT8E1H44PRMZ"}
│ ## First level files
├──the-plugin-name.php           # Main entry file for the plugin
├──composer.json                 # Composer dependencies & scripts
├──phpcs.xml.dist                # PHPCodeSniffer configuration
├──codeception.dist.yml          # Codeception testing configuration
├──.env.testing                  # Codeception testing environment configuration
├──.travis.yml                   # TravisCI configuration for automatic testing & continuous integration
├──package.json                  # (incl. when using webpack) Node.js dependencies & scripts (NPM functions)
├──webpack.config.js             # (incl. when using webpack) Holds all the base Webpack configurations
│
│ ## Folders
├──src                           # Holds all the plugin php classes
│   ├── Bootstrap.php            # Bootstraps the plugin and auto-instantiate classes
│   ├── App                      # Holds the plugin application-specific functionality
│   │   ├── Frontend             # All public-facing hooks/functionality
│   │   ├── Backend              # All admin-specific hooks/functionality
│   │   ├── General              # Hooks/functionality shared between the back-end and frontend
│   │   ├── Cli                  # Code for cli commands
│   │   ├── Cron                 # Code for cron events
│   │   ├── Rest                 # Code for rest api functionalities
│   ├── Config                   # Plugin configuration code
│   │   ├── Classes.php          # Defines the folders and order of classes to init
│   │   ├── I18n.php             # Internationalization and localization definitions
│   │   ├── Plugin.php           # Plugin data which are used through the plugin
│   │   ├── Requirements.php     # Defines the requirements that are needed to run this plugin.
│   │   ├── Setup.php            # Plugin setup hooks (activation, deactivation, uninstall)
│   ├── Common                   # Utilities & helpers shared in the whole plugin 
│   │   ├── Abstracts            # Here you can add abstract classes to extend your php classes
│   │   │   ├── Base.php         # A base class which all classes extends to load in default methods, currently the plugin data is only being injected
│   │   ├── Traits               # Here you can add handy traits to extend your php classes
│   │   │   ├── Requester.php    # The requester trait to determine what we request; used to determine which classes we instantiate in the Bootstrap class
│   │   │   ├── Singleton.php    # The singleton skeleton trait to instantiate the class only once
│   │   ├── Utils                # Here you can add helper/utiliy functions, eg: array functions
│   │   │   ├── Errors.php       # Utility class for the prettified errors and to write debug logs as string or array
│   │   ├── Functions.php        # Main function class for external/global functions, eg: "plugin_name()->your_function"
│   ├── Integrations             # Includes the integration with libraries, api's or other plugins
│   ├── Compatibility            # 3rd party compatibility code
├──tests                         # Codeception test files
├──templates                     # Folder to include all the template files
│   ├── test-template.php        # Example template file
├──languages                     # WordPress default language map in Plugins & Themes
│   ├── the-plugin-name.pot      # Boilerplate POT File that gets overwritten by WP-Pot 
├──webpack                       # (incl. when using webpack) Holds all the sub-config files for webpack
│   ├── .prettierrc.js           # Configuration for Prettier
│   ├── .eslintrc.js             # Configuration for Eslint
│   ├── .stylelintrc.js          # Configuration for Stylelint
│   ├── babel.config.js          # Configuration for BabelJS
│   ├── postcss.config.js        # Configuration for PostCSS
│   ├── config.base.js           # Base config for Webpack's development & production mode
│   ├── config.development.js    # Configuration for Webpack in development mode
│   └── config.production.js     # Configuration for Webpack in production mode
└──assets
    ├── src                      # (incl. when using webpack) Holds all the source files
    │   ├── images               # Uncompressed images
    │   ├── scss/pcss            # Holds the Sass/PostCSS files
    │   │ ├─ frontend.scss/pcss  # For front-end styling
    │   │ └─ backend.scss/pcss   # For back-end / wp-admin styling
    │   └── js                   # Holds the JS files
    │     ├─ frontend.js         # For front-end scripting
    │     └─ backend.js          # For back-end / wp-admin scripting
    │
    └── public
        ├── images               # Optimized (compressed) images
        ├── css                  # Compiled CSS files with be generated here
        └── js                   # Compiled JS files with be generated here
```
