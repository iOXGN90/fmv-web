# fmv_web
Fmv's Web

## Installation Steps

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

