# Portfolio Blazor WebAssembly: Déploiement Automatisé via GitHub Pages
## Description du Projet:
J'ai créé un portfolio utilisant Blazor WebAssembly, déployé automatiquement sur GitHub Pages. Le processus de déploiement est déclenché par les actions GitHub sur les événements PUSH, PULL Request et CRON sur la branche master.

## Détails Techniques:
  - Fichiers de Workflow: Situés dans la branche master sous .github/workflows/.
  - Fichier Original: [ilovedotnet/.github/workflows/deployment.yml](https://github.com/ILoveDotNet/ilovedotnet/blob/main/.github/workflows/deployment.yml)
  - Modifications: Simplification pour inclure uniquement les étapes de build et déploiement de WebAssembly.
## Ajouts pour GitHub Pages:
### Gestion des Erreurs 404:
``` yaml
      # touch 404.html & .nojekyll
      - name: touch 404.html & .nojekyll
        run: |
            touch dist/Capybara/wwwroot/.nojekyll
            cp dist/Capybara/wwwroot/index.html dist/Capybara/wwwroot/404.html
```
### Réécriture du chemin de base:
``` yaml
      # Rewrite base href        
      - name: Rewrite base href
        uses: SteveSandersonMS/ghaction-rewrite-base-href@v1
        with:
          html_path: dist/Capybara/wwwroot/index.html
          base_href: /
```

Ces ajouts gèrent les erreurs 404 sur GitHub Pages et réécrivent le chemin de base de l'application Blazor WebAssembly. Des mises à jour régulières sont effectuées pour tester et faire découvrir Blazor WebAssembly.

## Lien vers le Portfolio:
[Portfolio Blazor WebAssembly](https://yangyichengfelix.github.io)


   
