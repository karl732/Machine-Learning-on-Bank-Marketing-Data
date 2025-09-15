# 📋 Guide de mise en ligne GitHub

## Étapes pour publier votre projet sur GitHub

### 1. Préparation locale (déjà fait ✅)
- [x] `.gitignore` créé
- [x] `README.md` rédigé
- [x] `LICENSE` ajouté
- [x] `requirements.txt` listé
- [x] Repository Git initialisé

### 2. Nettoyage avant publication

```bash
# Supprimer les fichiers de cache volumineux (optionnel)
rm -rf *_cache/
rm -rf *_files/
rm *.RData *.Rdata
```

### 3. Ajout des fichiers au repository

```bash
# Ajouter tous les fichiers (sauf ceux dans .gitignore)
git add .

# Vérifier les fichiers ajoutés
git status

# Premier commit
git commit -m "🎉 Initial commit: Bank Marketing Analysis project

- ✨ Complete Quarto presentation with RevealJS
- 🤖 Multiple ML models: KNN, SVM, Random Forest, XGBoost
- 📊 Custom visualizations and themes
- 📚 Comprehensive documentation
- 🎨 Modern UI with responsive design"
```

### 4. Créer le repository sur GitHub

1. **Aller sur GitHub.com**
2. **Cliquer sur "New repository"**
3. **Paramètres suggérés :**
   - **Name:** `bank-marketing-analysis`
   - **Description:** `🏦 Machine Learning analysis of Portuguese bank marketing campaigns - Predicting term deposit subscriptions`
   - **Public** ✅ (ou Private si souhaité)
   - **Ne pas** initialiser avec README (déjà créé)

### 5. Connecter et pousser vers GitHub

```bash
# Ajouter l'origine GitHub (remplacer YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/bank-marketing-analysis.git

# Pousser vers GitHub
git branch -M main
git push -u origin main
```

### 6. Configuration du repository GitHub

#### A. Activer GitHub Pages (pour la présentation)
1. Repository → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** → **/ (root)**
4. Save

#### B. Ajouter des topics
Repository → **About** (roue dentée) → **Topics:**
- `machine-learning`
- `data-science`
- `r`
- `quarto`
- `bank-marketing`
- `classification`
- `revealjs`

#### C. Créer des templates d'issues (optionnel)
```bash
mkdir .github/ISSUE_TEMPLATE
```

### 7. URL de votre projet

Après publication, votre projet sera accessible à :
- **Repository:** `https://github.com/YOUR_USERNAME/bank-marketing-analysis`
- **Présentation:** `https://YOUR_USERNAME.github.io/bank-marketing-analysis/Quarto-Bank-Marketing-Pierre-et-Karl.html`

### 8. Commandes Git utiles pour la suite

```bash
# Ajouter des modifications
git add .
git commit -m "📝 Update: description des changements"
git push

# Créer une branche pour nouvelles features
git checkout -b feature/nouvelle-feature
git push -u origin feature/nouvelle-feature

# Revenir à la branche principale
git checkout main
```

### 9. Badges pour le README (optionnel)

Ajouter dans le README.md :
```markdown
[![GitHub stars](https://img.shields.io/github/stars/YOUR_USERNAME/bank-marketing-analysis.svg?style=social&label=Star)](https://github.com/YOUR_USERNAME/bank-marketing-analysis)
[![GitHub forks](https://img.shields.io/github/forks/YOUR_USERNAME/bank-marketing-analysis.svg?style=social&label=Fork)](https://github.com/YOUR_USERNAME/bank-marketing-analysis/fork)
```

## ✅ Checklist finale

- [ ] Repository créé sur GitHub
- [ ] Code poussé avec succès
- [ ] README.md affiché correctement
- [ ] GitHub Pages configuré (si souhaité)
- [ ] Topics ajoutés
- [ ] Présentation accessible en ligne

**Félicitations ! Votre projet est maintenant prêt pour GitHub ! 🎉**
