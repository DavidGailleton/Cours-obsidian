# Eslint prettier

Pour rendre son code conmpréhensible par tout le monde on utilise Eslint et prettier :
```shell
pnpm add -D eslint prettier eslint-config-prettier eslint-plugin-prettier
```

Puis on le configure dans .eslintrc.cjs :
```js
extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react-hooks/recommended',
    'plugin:prettier/recommended',
  ],
```
On créer un fichier .prettierrc.json :
```json
{
  "printWidth": 100, //fera automatiquement un retour a la ligne après 100 caractères sur la meme ligne
  "singleQuote": true, //mettra des simple quote a la place des doubles
  "semi": true, 
  "tabWidth": 2, // mettra 2 espaces par tabulation
  "trailingComma": "all",
  "endOfLine": "auto"
}
```

Pour terminer la configuration de prettier, il faut regarder la configuration dans les paramètres de l'IDE en foncton de l'IDE.

