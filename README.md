# Red Hat Quick Courses Contributor Guide

Welcome to the Red Hat Quick Courses contributor guide! This website uses standard asciidoc for content authoring that is then rendered to HTML and hosted by GitHub Pages. It uses the Antora publishing platform (https://antora.org) to transform the asciidoc conent to HTML.

To contribute, you can use locally installed tooling (Node.js runtime) on your workstation.

## Installing the development tooling

1. Install an LTS version of the Node.js runtime on your workstation. We recommend using **nvm** (https://github.com/nvm-sh/nvm) to manage your Node.js runtime.

2. Clone this Git repository to a folder of your choice. For the following steps in this README, this folder is indicated by *$CONTENT_ROOT*.
3. Install an editor of your choice. We recommend Visual Studio Code with the *asciidoctor* plug-in.
4. Follow the steps in the [*Previewing HTML content and publishing*](#Previewing-HTML-content-and-publishing) section.

> NOTE: At this point in time, only Mac OS and Linux operating systems have been tested. If you run Windows, you are on your own!

## Previewing HTML content and publishing

1. All commands in the following steps are to be run from the *$CONTENT_ROOT* folder. Navigate to this folder from the VSCode terminal (Press **"Ctrl + \`"** on Linux; Press **"Ctrl + Shift + `"** on MacOS):

```bash
$ cd $CONTENT_ROOT
```

2. Run **npm install** to install the Node.js dependencies for the project.

```bash
$ npm install
```

3. The Git repository contains the default chapter and section stubs with comments from the course product owner and architect to help guide you. Inspect the *$CONTENT_ROOT/antora.yml* file, which defines the top level modules (chapters) in this course. 

4. The starting point (index page) for the course is rendered from asciidoc content in the *modules/ROOT/pages/index.adoc* file.

5. Each top level module has a separate asciidoc file (*nav.adoc*) located in *modules/module_name/* folder. The *nav.adoc* lists the sections that make up the chapter/module.

6. Edit the asciidoc files under *$CONTENT_ROOT/modules/module_name/pages*. You can use the *asciidoctor* plug-in preview plugin (Press **"Ctrl + Shift + V"** on Linux; Press **"Cmd + Shift + V"** on MacOS) to preview the rendered HTML content.

7. To preview the rendered website as it would look for end-users consuming this content, do the following:

    * Run the **npm run watch:adoc** command to automatically detect changes to your asciidoc content and invoke the Antora HTML generator:

    ```bash
    $ npm run watch:adoc
    ```

    * In another termainal window, run the **npm run serve** command that starts a local web server that serves the generated HTML content:

    ```bash
    $ npm run serve
    ```
    You will be shown the local URL where you can view the rendered content. Open the link in a web browser.

    * Keep making changes in your asciidoc source files. The **npm watch** command will automatically detect your changes and re-generate the HTML content. Refresh your web browser to view the updated content

8. Once you are satisfied with how the HTML content is rendered locally in your workspace, you can commit your changes and do a **git push** to your branch.

9. Open a Pull Request so that the changes in your branch can be merged into the **main** branch of this Git repository. A GitHub action runs on every merge & push to the **main** branch and publishes the HTML content to a GitHub Page.

9. After a few minutes, the GitHub action finishes and you can view the latest rendered contributor guide at https://redhatquickcourses.github.io/ 

## Problems and Feedback
If you run into any issues, report bugs/suggestions/improvements about this course here - https://github.com/RedHatQuickCourses/redhatquickcourses.github.io/issues
