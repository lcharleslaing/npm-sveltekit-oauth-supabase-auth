# Sveltekit/OAuth/Supabase Authentication Package

This package adds all needed files to add OAuth/Supabase Authentication to your Sveltekit project (See Below for Create-Svelte to create your project if you do not already have it created).

## Create-Sveltekit

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

### Creating a project

If you're seeing this, you've probably already done this step. Congrats!

### create a new project in the current directory

```bash
npm create svelte@latest
```

or

### create a new project in my-app

or

```bash
npm create svelte@latest my-app
```

or

### create a new project in current project directory

```bash
npm create svelte@latest .
```

## Styling w/[Svelte-Add](https://github.com/svelte-add/svelte-add.git) packages

I am a fan of [TailwindCSS and DaisyUI](https://github.com/svelte-add/tailwindcss.git) but if you want other options click [here](https://github.com/svelte-add/svelte-add.git) to see them.

So I use the below command to install my preferences.

### **TailwindCSS (with Forms & Typography) & DaisyUI**

```bash
npx svelte-add@latest tailwindcss --tailwindcss-forms --tailwindcss-typography --tailwindcss-daisyui
```

or

### **TailwindCSS (only) & DaisyUI**

```bash
npx svelte-add@latest tailwindcss --tailwindcss-daisyui
```

### Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

### Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

## Install the Sveltekit/OAuth/Supabase Authentication Package

```bash
npx install sveltekit-oauth-supabase-auth
npm i
```

or

```bash
npx add sveltekit-oauth-supabase-auth
npm i
```

### ./example.env

```env
# ./example.env

# Supabase Database URL
DATABASE_URL=your_database_url

# Supabase URL and Key
PUBLIC_SUPABASE_URL=your_supabase_url
PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

# OAuth Auth Secret Key that you will need to provide here.  Once it is set, it should not be changed.
AUTH_SECRET=your_auth_secret

# Github OAuth Keys
VITE_GITHUB_ID=your_github_id
VITE_GITHUB_SECRET=your_github_secret

# Google OAuth Keys
VITE_GOOGLE_CLIENT_ID=your_google_client_id
VITE_GOOGLE_CLIENT_SECRET=your_google_client_secret

```

- Rename **example.env** to **.env** if you have not created a **.env** file yet.
- If you already have a **.env**, then copy the .env contents to your exxisting **.env** file.

- Get your [Google](https://console.cloud.google.com/apis/credentials) and [Github](https://github.com/settings/developers) credentials from the respective sites and update the .env with your credentials.
