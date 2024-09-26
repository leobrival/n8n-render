# n8n-render (easy mode)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

### How to install n8n on render.com for free

Follow these steps :

1. Click on the render button above
2. Choose a blueprint name, for exemple "n8n"
3. Click on "Create New Ressources"
4. Apply
5. Go to Dashboard > n8n (your service name) > Environment
6. Copy your URL (purple link in header).
7. Past your URL as value for WEBHOOK_URL
8. Wait a minute for your instance to update
   Ajouter un CRON de 10 min scénario pour taper la route ${WEBHOOK_URL}/healthz pour activer constinuellement render et eviter la veille
9. Enjoy !

Created by Léo Brival for Topographic Studio. Inspired by ready4mars.

Créer un compte sur Supabase et créer une base de donnée postgres
Remplir les variables d'environnement avec les variables de la base de donnée Supabase
https://www.youtube.com/watch?v=e1qz50cq-s4
