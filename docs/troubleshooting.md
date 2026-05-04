# Depannage

## Le Dashboard Ne Charge Pas

Verifier :

```text
http://localhost:8005/api/stats/
```

Si cette route ne repond pas, relancer FastAPI.

## Swagger Fonctionne Mais Pas L'Interface

Verifier que l'URL backend dans `src/lib/api.ts` est correcte :

```ts
baseURL: "http://localhost:8005"
```

## Le Mode Hybride Ne Retourne Rien

Le mode hybride Weaviate peut appeler VoyageAI en temps reel. Verifier :

- DNS Docker ;
- acces internet du conteneur Weaviate ;
- variable `VOYAGEAI_APIKEY` ;
- disponibilite de `api.voyageai.com`.

Le mode `vecteur` reste le plus stable si les donnees sont deja vectorisees.

## Le Reranking Echoue

Verifier :

```text
VOYAGEAI_APIKEY
```

Puis tester :

```text
POST /api/search/rerank/
```

## Upload Candidat Retourne 422

Cela signifie que le backend n'a pas pu extraire un nom valide.

Verifier :

- qualite du fichier ;
- premiere ligne du CV ;
- logs `[Upload] full_name`;
- presence de texte extractible.

## Weaviate Non Disponible

Verifier Docker :

```powershell
docker ps
```

Puis verifier que les ports sont exposes correctement.
