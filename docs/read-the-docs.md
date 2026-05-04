# Publication Read The Docs

Cette documentation est prete pour un deploiement sur Read the Docs.

## Fichiers De Configuration

La configuration principale se trouve a la racine du projet :

```text
.readthedocs.yaml
```

Elle indique a Read the Docs d'utiliser :

```text
cv-scanner-godev/mkdocs.yml
```

Les dependances de documentation sont listees ici :

```text
cv-scanner-godev/docs/requirements.txt
```

## Etapes De Publication

1. Pousser le projet sur GitHub ou GitLab.
2. Creer un compte sur Read the Docs.
3. Importer le depot.
4. Verifier que Read the Docs detecte `.readthedocs.yaml`.
5. Lancer un build.
6. Ouvrir l'URL publique generee.

## Commande Locale Equivalente

Pour tester localement :

```powershell
cd cv-scanner-godev
pip install -r docs/requirements.txt
mkdocs serve
```

La documentation sera disponible sur :

```text
http://127.0.0.1:8000
```
