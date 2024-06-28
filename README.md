# FMV Website

# FMV's Background ❔❔❔

    Management systems are crucial for companies to efficiently track transactions, record events, and maintain comprehensive activity records. Various types, like ERP, IMS, and HRMS, integrate multiple functions into a centralized platform, offering features like inventory management, payroll processing, CRM, and order tracking. These systems enhance overall performance, operational efficiency, and data accuracy. A study by Zgirskas et al. (2021) showed significant benefits for businesses adopting management systems, including improved product quality, fewer incidents, increased profitability, and better customer satisfaction.

    Francis Mar Vincent (FMV) Drilling Industries, owned by Wilmar Bucoo Indonto, provides plumbing services and supplies to government and private clients, handling up to 10 orders per week from 1252 items. Based in Cagayan de Oro City with a sub-branch in Bohol and 15 employees, FMV serves the Mindanao region using various transportation methods.

    Currently, FMV relies on forms and spreadsheets for order processing, inventory management, and attendance monitoring, which are prone to human error and data loss. Clients submit purchase orders, which are manually entered into spreadsheets to request stock and generate invoices, delivery receipts, and official receipts. Attendance is tracked through daily staff signatures to calculate wages.

    To address these issues, a proposed solution involves developing an integrated management system, including an inventory system and a mobile delivery application. This system aims to be user-friendly for FMV's admin and employees, who are not well-versed in technology. An inventory management system is vital for tracking stock levels and centralizing availability. Srivastava et al. (2020) highlighted problems like missing items and poor inventory control in businesses without such systems. The proposed mobile application will enable real-time tracking of inventory movement and status updates.

## Installation Steps of `"Tailwind"`

1. Initialize npm:
    ```sh
    npm init -y
    ```

2. Install Tailwind CSS and its dependencies:
    ```sh
    npm install -D tailwindcss postcss autoprefixer
    ```

3. Initialize Tailwind CSS configuration:
    ```sh
    npx tailwindcss init -p
    ```
4. ### Configuration

### `src/css/styles.css`:
```css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
```

`tailwind.config.js`:
```js
    module.exports = {
    content: [
        './pages/**/*.html',
        './src/**/*.css',
    ],
    theme: {
        extend: {},
    },
    plugins: [],
    }
```
`package.json`:
```json
{
  "name": "fmv_web",
  "version": "1.0.0",
  "scripts": {
    "build": "postcss src/css/styles.css -o pages/css/styles.css",
    "watch": "postcss src/css/styles.css -o pages/css/styles.css --watch"
  },
  "devDependencies": {
    "tailwindcss": "^3.x.x",
    "postcss": "^8.x.x",
    "autoprefixer": "^10.x.x",
    "postcss-cli": "^9.x.x"
  }
}
```
# Build CSS

5. Run the following command to compile your CSS:

    ```sh
    npm run build
    ```
    Note, if the tailwind's design isn't applying, run this:

        npx postcss src/css/styles.css -o pages/css/styles.css



# Directory Structure

6. The directory structure should look like this:
```bash
    fmv_web/
    ├── node_modules/
    ├── pages/
    │   ├── css/
    │   │   └── styles.css  # Compiled CSS file
    │   └── index.html      # Your HTML file
    ├── src/
    │   └── css/
    │       └── styles.css  # Source CSS file with Tailwind directives
    ├── package.json
    ├── postcss.config.js
    ├── tailwind.config.js
    └── .gitignore
```

# index.html 
7. This is a sample to initiate the style:
```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page</title>
    <link href="css/styles.css" rel="stylesheet"> ///This will load the styles of the css that is found in the `pages/css/styles.css`
    </head>
    <body>
    <h1 class=" font-bold underline">
        Hello, Tailwind CSS!
    </h1>
    </body>
    </html>
```
-------------------------------------------------------------------------------

# Additional Steps

Since sige man tag `npm run build` kada naay changes sa atong designs, naa koy life hacks, follow lang.

1. install: 
```sh
    npm install -D concurrently

    npm install -D browser-sync browser-sync-webpack-plugin
```

2. Create a file, `bs-config.js` and inside fmv_web/bs-config.js:
```js
    module.exports = {
        proxy: "localhost:3000", // Adjust this to your local server address if needed
        files: ["pages/**/*.html", "pages/css/**/*.css"],
        open: false,
        notify: false
    };
```

3. The package.json:
```json
{
  "name": "fmv_web",
  "version": "1.0.0",
  "scripts": {
    "build": "postcss src/css/styles.css -o pages/css/styles.css",
    "watch:css": "postcss src/css/styles.css -o pages/css/styles.css --watch",
    "watch:bs": "browser-sync start --config bs-config.js",
    "watch": "concurrently \"npm run watch:css\" \"npm run watch:bs\"",
    "start": "npm run watch"
  },
  "devDependencies": {
    "tailwindcss": "^3.x.x",
    "postcss": "^8.x.x",
    "autoprefixer": "^10.x.x",
    "postcss-cli": "^9.x.x",
    "concurrently": "^6.x.x",
    "browser-sync": "^2.x.x",
    "browser-sync-webpack-plugin": "^2.x.x"
  }
}

```

4. Run the following: 
```sh
    npm start
```

# Directory Structure (UPDATED)

```bash
    fmv_web/
    ├── node_modules/
    ├── pages/
    │   ├── css/
    │   │   └── styles.css  # Compiled CSS file
    │   └── index.html      # Your HTML file
    ├── src/
    │   └── css/
    │       └── styles.css  # Source CSS file with Tailwind directives
    ├── package.json
    ├── postcss.config.js
    ├── tailwind.config.js
    ├── bs-config.js
    └── .gitignore
```

# Notes

    This `README.md` should guide users through setting up the project and automating the build process with live reload. If you have any more instructions or need further adjustments, igna lang ko!
