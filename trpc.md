## Create a trpc project 
```
npx create-turbo@latest "Project-Name"
```
or
```
pnpm dlx create-turbo@latest
```
[Link](https://turborepo.dev/docs/getting-started/installation)
### Note: Choose pnpm

### Insatll the dependencies
```
pnpm install
```
### Build the Project
```
pnpm run build
```
### Run the Project
```
pnpm run dev
```

## Create utils in "packages"
```code
utils/package.json
utils/src
```

```json
{
    "name": "@myapp/utils",
    "version": "0.0.1",
    "main": "./src/index.ts",
    "types": "./src/index.ts",
    "exports": {
        ".": {
            "import": "./src/index.ts",
            "require": "./src/index.ts",
            "default": "./src/index.ts"
        }
    }
}
```
