# 🚀 Guide d'installation

## Prérequis

### 1. R et RStudio
- **R** >= 4.2.0 : [Télécharger R](https://cran.r-project.org/)
- **RStudio** (recommandé) : [Télécharger RStudio](https://posit.co/products/open-source/rstudio/)

### 2. Quarto
- **Quarto** >= 1.2.0 : [Télécharger Quarto](https://quarto.org/docs/get-started/)

## Installation des packages R

### Option 1 : Installation automatique
```r
# Copier-coller ce code dans la console R
packages <- c(
  "tidyverse", "tidymodels", "caret", "randomForest", 
  "e1071", "kernlab", "xgboost", "MASS", "class",
  "ggplot2", "ggpubr", "ggthemes", "patchwork", 
  "viridis", "scales", "RColorBrewer",
  "pROC", "plotROC", "ROCR", "precrec", "yardstick",
  "rpart", "rpart.plot", "tree", "ada", "kknn", "discrim",
  "FactoMineR", "factoextra", "corrplot",
  "knitr", "kableExtra", "DT",
  "parallel", "doParallel", "MLmetrics", "DMwR2",
  "questionr", "visdat", "tinytex"
)

install.packages(packages, dependencies = TRUE)
```

### Option 2 : Installation depuis requirements.txt
```r
# Lire le fichier requirements.txt et installer
packages <- readLines("requirements.txt")
packages <- packages[!grepl("^#|^$", packages)]  # Enlever commentaires
packages <- gsub(">=.*", "", packages)           # Enlever versions
install.packages(packages, dependencies = TRUE)
```

## Vérification de l'installation

```r
# Tester les packages principaux
library(tidyverse)
library(tidymodels)
library(ggplot2)
library(caret)
library(randomForest)

cat("✅ Installation réussie !\n")
```

## Utilisation

### 1. Cloner le repository
```bash
git clone https://github.com/votre-username/bank-marketing-analysis.git
cd bank-marketing-analysis
```

### 2. Ouvrir le projet dans RStudio
- Ouvrir RStudio
- File → Open Project → Sélectionner le dossier du projet

### 3. Générer la présentation
```r
# Dans RStudio
# Ouvrir "Quarto Bank Marketing Pierre et Karl.qmd"
# Cliquer sur "Render" ou utiliser Ctrl+Shift+K
```

Ou en ligne de commande :
```bash
quarto render "Quarto Bank Marketing Pierre et Karl.qmd"
```

## Résolution de problèmes

### Erreur de packages manquants
```r
# Installer un package spécifique
install.packages("nom_du_package")
```

### Erreur Quarto
```r
# Installer/Mettre à jour Quarto
# Télécharger depuis https://quarto.org/docs/get-started/
```

### Conflits de packages
```r
# Redémarrer R et recharger les packages
.rs.restartR()
```

## Support

Consultez [README_Troubleshooting.md](README_Troubleshooting.md) pour les problèmes spécifiques au projet.
