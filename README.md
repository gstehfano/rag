name: Deploy to Server

on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Build and Deploy
        run: |
          npm install
          npm run build
          curl -X POST https://seu-servidor-de-deploy.com/deploy
