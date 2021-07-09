# SvelteKit app with docker-compose test

I try to make SvelteKit Skeleton app which is created by `npm init svelte@next app` into docker image.

## Just npm run build on localhost

### Step 1. create skeleton app
```
> cd app-server
> npm init svelte@next app

create-svelte version 2.0.0-next.73

Welcome to SvelteKit!✔ Which Svelte app template? › Skeleton project
✔ Use TypeScript? … Yes
✔ Add ESLint for code linting? … Yes
✔ Add Prettier for code formatting? … Yes
```
### Step 2. add node adapter kit
Refer to sveltekit website [doc](https://kit.svelte.dev/docs#adapters) and adapter-node github [doc](https://github.com/sveltejs/kit/tree/master/packages/adapter-node), tweaks *app-server/app/svelteconfig.json* as below, then run ```npm i -D @sveltejs/adapter-node@next``` get the *app-server/app/package.json* updated

```
import node from '@sveltejs/adapter-node';

export default {
	kit: {
		adapter: node()
	}
};
```

## To create and run docker image 

### Development
We can build and run the Welcome svelteKit app in docker container by using ```docker-compose -f docker-compose.dev.yml up``` successfully.

### Production (It's work at copy-app-output branch)
To apply production we use just ```docker-compose up```

