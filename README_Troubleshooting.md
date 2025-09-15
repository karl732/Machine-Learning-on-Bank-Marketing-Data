# 🔧 Guide de dépannage - Présentation Bank Marketing

## Problème résolu : Conflit `margin()`

### ❌ **Erreur rencontrée**
```
Error in `margin.default()`:
! l'argument "observed" est manquant, avec aucune valeur par défaut
```

### 🔍 **Cause**
Conflit entre `ggplot2::margin()` et `randomForest::margin()` - deux fonctions avec le même nom mais des usages différents.

### ✅ **Solution appliquée**

1. **Spécification explicite du namespace** dans le thème :
   ```r
   margin = ggplot2::margin(b = 20)  # Au lieu de margin(b = 20)
   ```

2. **Ordre de chargement optimisé** des packages :
   ```r
   library(ggplot2)     # D'abord ggplot2
   # ... autres packages ...
   library(randomForest) # randomForest en dernier
   ```

3. **Version robuste du thème** avec assignation locale :
   ```r
   gg_margin <- ggplot2::margin  # Assignation locale
   margin = gg_margin(b = 20)    # Utilisation sécurisée
   ```

## 🚀 **Instructions d'utilisation**

### Pour compiler la présentation :
1. Ouvrir RStudio
2. Ouvrir le fichier `Quarto Bank Marketing Pierre et Karl.qmd`
3. Cliquer sur "Render" ou utiliser Ctrl+Shift+K
4. Ou en ligne de commande : `quarto render "Quarto Bank Marketing Pierre et Karl.qmd"`

### En cas de nouveaux conflits :
1. Vérifier l'ordre de chargement des packages
2. Utiliser `::` pour spécifier le namespace
3. Utiliser le package `conflicted` si nécessaire :
   ```r
   library(conflicted)
   conflict_prefer("margin", "ggplot2")
   ```

## 🎨 **Améliorations apportées**

- ✅ Configuration optimisée pour RevealJS
- ✅ Thème personnalisé moderne
- ✅ Palettes de couleurs harmonieuses
- ✅ Graphiques adaptés aux dimensions d'écran
- ✅ CSS personnalisé pour l'esthétique
- ✅ Résolution des conflits de packages

## ❌ **Nouveau problème résolu : Erreur "truth must be a factor"**

### 🔍 **Erreur rencontrée**
```
Error: `truth` should be a factor but a <type> was supplied
```

### 🔍 **Cause**
La variable `y` n'était pas correctement formatée comme un facteur dans les données de test, ce qui est requis par les fonctions `accuracy()`, `conf_mat()`, et `roc_auc()` de tidymodels.

### ✅ **Solution appliquée**

1. **Conversion explicite en facteur** avant le split :
   ```r
   data_boost$y <- as.factor(data_boost$y)
   ```

2. **Vérifications dans les prédictions** :
   ```r
   if (!is.factor(boost_fit_on_test$y)) {
     boost_fit_on_test$y <- as.factor(boost_fit_on_test$y)
   }
   ```

3. **Cohérence des niveaux** entre truth et estimate :
   ```r
   boost_fit_on_test$.pred_class <- factor(boost_fit_on_test$.pred_class, 
                                          levels = levels(boost_fit_on_test$y))
   ```

## 📞 **Support**
Si d'autres problèmes surviennent, vérifiez :
1. Les versions des packages R
2. L'ordre de chargement
3. Les conflits de noms de fonctions
4. Le format des variables (facteur vs character/numeric)
5. La cohérence des niveaux de facteurs
