# holo-tcg
A web app for simulating the Hololive Trading Card Game

## Currently working on:
- Stage Interface
- Card Elements
- Damage Tracker Functionality

## Versions
| Program  | Version |
| -------- | ------- |
| node.js  | 20.18.0 |
|   npm    | 10.9.0  |

## Installation Guide (by ChatGPT)
### Step-by-Step Guide to Create a Next.js React App

#### 1. **Set Up Node.js and npm**
Make sure you have **Node.js** installed on your machine before starting. You can download it from [Node.js official site](https://nodejs.org/).

To check if you have Node.js and npm installed, run:

```bash
node -v
npm -v
```

#### 2. **Create a Next.js App Using `create-next-app`**
To create a new Next.js project, you’ll use the `create-next-app` tool. Run the following command in your terminal:

```bash
npx create-next-app@latest my-next-app
```

This command will set up a new Next.js project in a folder called `my-next-app`. It will prompt you to answer a few questions:

- **TypeScript**: Whether you want to use TypeScript (you can start with JavaScript and add TypeScript later).
- **ESLint**: Whether to set up ESLint to catch coding errors.
- **Tailwind CSS**: Whether to include Tailwind CSS for styling.
- **src directory**: If you want to organize your project by using a `/src` directory.
- **Experimental features**: Optionally enable any experimental features.

Once this is done, it will install all the necessary dependencies for you.

#### 3. **Navigate to Your Project Directory**
Once the setup is complete, move into the newly created project folder:

```bash
cd my-next-app
```

#### 4. **Run the Development Server**
To see your Next.js app running, use the following command:

```bash
npm run dev
```

This starts the development server, and the app will be available at `http://localhost:3000/`.

#### 5. **Explore the Folder Structure**
Next.js has a specific project structure that revolves around `pages`, which are automatically routed.

- **pages/**: Contains all the React components that represent routes.
  - For example, `pages/index.js` is the homepage, accessible at `http://localhost:3000/`.
- **public/**: For static files like images, fonts, etc.
- **styles/**: Contains styles for your application.

#### 6. **Create New Pages (Routing in Next.js)**
To create a new page, simply add a new file in the `pages` directory. For example, to create an "About" page, create a new file called `about.js` inside `pages`:

```jsx
// pages/about.js
export default function About() {
  return <h1>About Us</h1>;
}
```

This will create a new route accessible at `http://localhost:3000/about`.

#### 7. **Linking Between Pages**
You can link between pages using Next.js’s built-in `Link` component:

```jsx
import Link from 'next/link';

export default function Home() {
  return (
    <div>
      <h1>Home Page</h1>
      <Link href="/about">Go to About Page</Link>
    </div>
  );
}
```

#### 8. **Static and Server-Side Rendering**
Next.js allows you to choose between static generation (SSG) and server-side rendering (SSR).

- **Static Generation** (SSG): Pages are pre-rendered at build time.
- **Server-Side Rendering** (SSR): Pages are rendered at the time of the request.

To enable static generation with data fetching in Next.js:

```js
// pages/index.js
export async function getStaticProps() {
  const data = await fetchData();
  return {
    props: {
      data,
    },
  };
}

export default function Home({ data }) {
  return <div>{data}</div>;
}
```

To enable server-side rendering:

```js
// pages/index.js
export async function getServerSideProps() {
  const data = await fetchData();
  return {
    props: {
      data,
    },
  };
}

export default function Home({ data }) {
  return <div>{data}</div>;
}
```

#### 9. **Styling Your Next.js App**
You can style your Next.js app using CSS, Sass, or CSS-in-JS libraries like styled-components.

- **Global CSS**: Add global styles in `styles/globals.css`.
- **CSS Modules**: You can use component-specific styles by creating `.module.css` files and importing them inside components.

Example:

```jsx
// pages/index.js
import styles from './Home.module.css';

export default function Home() {
  return <h1 className={styles.title}>Welcome to Next.js!</h1>;
}
```

#### 10. **Deploying Your Next.js App**
Once your app is ready, you can deploy it to platforms like Vercel, which is optimized for Next.js, or use GitHub Pages for static deployments.

- **Deploying to Vercel**:
   1. Push your Next.js project to GitHub.
   2. Go to [Vercel](https://vercel.com/), sign up, and import your repository.
   3. Vercel automatically detects Next.js and sets up the deployment process.

- **Deploying to GitHub Pages**:
   1. You’ll need to export the static version of your Next.js app by adding this script to your `package.json`:

      ```json
      "scripts": {
        "build": "next build",
        "export": "next export"
      }
      ```

   2. Run the export command:

      ```bash
      npm run build && npm run export
      ```

   3. This will generate a `out` folder. You can push this folder to the `gh-pages` branch of your GitHub repository to host it using GitHub Pages.
