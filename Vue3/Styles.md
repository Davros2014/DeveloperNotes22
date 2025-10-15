
## **Styling with external CSS or SASS files**

To import a CSS file from an external source and make it available globally to components in a Vue 3 application, you can include the CSS file in your project's main entry file, typically `main.js` or `main.ts` if you're using TypeScript. 

1. **Direct Import in `main.js` or `main.ts`**: If the CSS file is hosted online, you can download it and place it in your project, or if it's a package you installed via npm, you can import it directly.
    
    - **For a Local CSS File**: First, place the CSS file in your project, for example, in the `assets` folder. Then, import it in your `main.js` or `main.ts` file.
        
        // Assuming the CSS file is located at src/assets/your-stylesheet.css
        
        import './assets/your-stylesheet.css';
        
    - **For an npm Package**: If the CSS is part of a library you installed, you can import it directly by its path in the `node_modules` directory.
        
        // For example, importing Bootstrap CSS
        
        import 'bootstrap/dist/css/bootstrap.min.css';
        
2. **Using a CDN**: If you prefer to use a CDN, you can include the CSS link in your `public/index.html` file. This method doesn't involve `main.js` or `main.ts`, but it ensures the CSS is available globally.
    
    <!-- Add this in the <head> section of public/index.html -->
    
    <link rel="stylesheet" href="https://example.com/path/to/your-stylesheet.css">
    

By importing the CSS file in the `main.js` or `main.ts` file, the styles will be applied globally across all components in your Vue 3 application. If you include it via a CDN in the `index.html`, it also becomes globally available but is loaded from an external source each time your application is accessed.


-----------------------------------------------------------------------

## **Using CSS files from a location outside the root directory**

If the CSS file is outside the root directory of your Vue 3 project and you want to make it available to the project and its components, you have a few options depending on your project setup and build tools (like Webpack, Vite, etc.)

#### 1. **Copy the CSS File into Your Project**

The simplest approach is to copy the CSS file into your project's directory structure, such as into the [`src/assets`](vscode-file://vscode-app/c:/Users/ArajarDW/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html "c:\Users\ArajarDW\Vue3\figmaToVue\figmaTest\src\assets") folder. This way, you can import it directly in your `main.js` or `main.ts` file as described previously.

#### 2. **Use a Symbolic Link**

You can create a symbolic link (symlink) in your project directory that points to the CSS file's actual location. This makes the file appear as if it's part of your project structure, allowing you to import it normally.

- **On Windows:**
    
    mklink Link Target
    
    For example, if your project is in `C:\Projects\MyVueApp` and the CSS file is `D:\SharedStyles\styles.css`, you can create a symlink in your project like this:
    
    cd C:\Projects\MyVueApp\src\assets
    
    mklink styles.css D:\SharedStyles\styles.css
    
- **On Linux/macOS:**
    
    ln -s Target Link
    
    Adjust the paths to fit your directory structure.

#### 3. **Configure Your Build Tool**

If you're using a build tool like Webpack or Vite, you can configure it to include files from outside your project directory. This approach requires modifying your build configuration to explicitly include the external path.

- **Webpack Example:** You can use the `copy-webpack-plugin` to copy the external CSS file into your build directory.
    
    const CopyPlugin = require("copy-webpack-plugin");
    
    module.exports = {
    
      plugins: [
    
        new CopyPlugin({
    
          patterns: [
    
            { from: 'path/to/external/css/file.css', to: 'path/inside/dist' },
    
          ],
    
        }),
    
      ],
    
    };
    
- **Vite Example:** Vite supports aliasing out of the box, but for copying files, you might need to use a plugin or manually copy the file as part of your build process.

#### 4. **Import Directly if Using a Module Bundler**

If your project setup and the external CSS file's location allow it, you might directly import the CSS file by specifying its relative path from your project's entry file, though this is less common for files outside the project root due to potential issues with module resolution.

### Note:

Each of these methods has its use cases and potential limitations based on your project's specific setup and environment. Copying the file or using a symlink is generally the simplest and most straightforward approach.

------------------------------------------------------

## **Using SCSS files natively in Vue3**

Requires setting up a pre-processor to compile SASS/SCSS to CSS. 

1. **Install SASS and the SASS loader**: You need to install `sass` and `sass-loader` as development dependencies in your project.
    
    npm install --save-dev sass sass-loader
    
2. **Use SASS in Vue Components**: After installing, you can use SASS within your Vue components by specifying the `lang="scss"` or `lang="sass"` attribute in the `<style>` tag.
    
    <style lang="scss">
    
    $color:  red;
    
    .example {
    
      color: $color;
    
    }
    
    </style>
    
3. **Global Styles**: If you want to use global styles (variables, mixins, etc.) across your components, you can create a SASS file (e.g., `global.scss`) and import it in your main entry file (`main.js` or `main.ts`) or directly into your components.
    
    - **Importing in `main.js`** (for global availability):
        
        import './assets/styles/global.scss';
        
    - **Importing in a Vue Component** (for use in that component only):
        
        <style lang="scss">
        
        @import "@/assets/styles/global.scss";
        
        .example {
        
          color: $color; // Variable from global.scss
        
        }
        
        </style>
        

This setup allows you to use SASS/SCSS in your Vue 3 project, enabling you to leverage the power of SASS for more dynamic and maintainable stylesheets.