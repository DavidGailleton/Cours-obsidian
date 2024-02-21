# Le [[css]] avec [[React]]

## Module
Pour associer un fichier CSS il le nommer en `{nom_du_fichier_cible}.module.css`

## Les class

Dans un fichier JS ou TS, `class` est un mot réservé.
Pour utiliser du css en html on vas utiliser `className` au lieu de class:
```tsx
export default function Alert() {
	return(
		<>
			<div className="App text-3xl">{message}</div>
			{
				type === 'Warning' && <div>Attention</div>
			}
    	</>
	)
}
```