## Feature eployment
1. Create a [Vercel account](https://vercel.com/signup) with your aceable account `user@aceable.com` 
2. Ask management to invite you to the Aceable team when you you already have your account.
3. When you accept the invite, go to https://vercel.com/account/tokens and create your token, copy your token
4. In Pyramid project, look for `providence/.env.local.example` and duplicate to create a copy of that file that will be `providence/.env.local`
5. In the file paste your Vercel token in variable, i.e `ZIET_NOW_TOKEN=XXxxxXXXxxxxXX`
### DEploy Process
1. You should be ready to create feature deployments, try to run `yarn deploy && yarn feature-local && cd tmp/src/dist && vercel` 
	1.  Select the project you want to deploy `driving` or `real-estate`
	2. Select `local` in the next step, next you project will be created on `tmp/src`
	3. In case you just run `yarn deploy`, run `yarn feature-local` when deploy finishes to generate the static, if you combine the commands it will be automated.
	4. When static generation is finished use `cd tmp/src/dist && vercel` to start the deployment (in case you don't combine the command), you will have the following questions:
		- `Set up and deploy` type [Y]
		- `Which scope do you want to deploy to` Select Aceable
		- `Found project “aceable/dist”. Link to it?` type [Y]
	When deploy finishes you will have a URL like: `https://vercel.com/aceable/dist/Gi3ZRS12AqS9bc96PAJULmW4oJWX` which will be the URL for your feature deployment.
