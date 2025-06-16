# Image Node officielle légère
FROM node:18-alpine

# Dossier de travail dans le container
WORKDIR /app

# Copier les fichiers du projet
COPY . .

# Installer les dépendances
RUN npm install

# Exposer le port utilisé par Vite
EXPOSE 5173

# Lancer le serveur Vite en mode dev et accessible depuis l'extérieur
CMD ["npm", "run", "dev", "--", "--host"]
