# create-svelte
```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app

npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

# Prisma
```bash
npm install --save-dev prisma@latest
npm install --save @prisma/client@latest

npx prisma init --datasource-provider sqlite

npx prisma db push
# Environment variables loaded from .env
# Prisma schema loaded from prisma/schema.prisma
# Datasource "db": SQLite database "dev.db" at "file:./dev.db"

npx prisma studio

# 데이터 넣기 : seed.ts 작성

# seed를 실행하기 위한 node 깔기
npm install --save-dev ts-node @types/node

# package.json
“prisma”: {
	“seed”: “node —loader ts-node/esm prisma/seed.ts"
}

# 실행
npx prisma db seed
```

# SvelteKit에서 Root 설정
```
# svelte.config.js
kit: {
	adapter: adapter(),
	alias: {
		$root: 'src'
	}
}

# tsconfig.json
"compilerOptions": {
	"baseUrl": ".",
	"paths": {
		"$root/*": ["./src/*"]
	}
},
"include": ["src/**/*.d.ts", "src/**/*.ts", "src/**/*.js", "src/**/*.svelte"]

# .prettierrc
{
	"semi": false,
	"printWidth": 60,
}
```