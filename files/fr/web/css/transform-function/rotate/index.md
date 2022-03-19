---
title: rotate()
slug: Web/CSS/transform-function/rotate
tags:
  - CSS
  - Fonction
  - Reference
  - Transformations CSS
translation_of: Web/CSS/transform-function/rotate()
original_slug: Web/CSS/transform-function/rotate()
---
{{CSSRef}}

La fonction **`rotate()`** définit une transformation qui déplace un élément autour d'un point fixe (défini par la propriété {{cssxref("transform-origin")}}) sans le déformer (autrement dit, qui applique une rotation plane). C'est une rotation autour de ce point. Par défaut, cette origine correspond au centre de l'élément.

La rotation plane est définie par un angle, l'argument de la fonction. Si l'angle indiqué est positif, le mouvement sera appliqué dans le sens horaire et sinon il sera appliqué dans le sens inverse des aiguilles d'une montre. La valeur obtenue par cette fonction est de type {{cssxref("&lt;transform-function&gt;")}}.

## Syntaxe

L'angle de la rotation créée grâce à `rotate()` est fourni comme argument à cette fonction via une valeur de type {{cssxref("&lt;angle&gt;")}}. Si l'angle est positif, la rotation sera dans le sens des aiguilles d'une montre et s'il est négatif, elle sera dans le sens inverse des aiguilles d'une montre.

    rotate(a)

### Valeurs

- _a_
  - : Une valeur de type {{cssxref("&lt;angle&gt;")}} qui représente l'angle de la rotation. Un angle positif indique une rotation appliquée dans le sens horaire, un angle négatif applique une rotation dans le sens anti-horaire.

<table class="standard-table">
  <thead>
    <tr>
      <th scope="col">Coordonnées cartésiennes surℝ<sup>2</sup></th>
      <th scope="col">Coordonnées homogènes sur ℝℙ<sup>2</sup></th>
      <th scope="col">Coordonnées cartésiennes sur ℝ<sup>3</sup></th>
      <th scope="col">Coordonnées homogènes sur ℝℙ<sup>3</sup></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="1" rowspan="2">
        <math
          ><mfenced
            ><mtable
              ><mtr><mtd>cos(a)</mtd><mtd>-sin(a)</mtd></mtr>
              <mtr><mtd>sin(a)</mtd><mtd>cos(a)</mtd></mtr></mtable
            ></mfenced
          ></math
        >
      </td>
      <td>
        <math
          ><mfenced
            ><mtable
              ><mtr><mtd>cos(a)</mtd><mtd>-sin(a)</mtd><mtd>0</mtd></mtr
              ><mtr><mtd>sin(a)</mtd><mtd>cos(a)</mtd><mtd>0</mtd></mtr
              ><mtr><mtd>0</mtd><mtd>0</mtd><mtd>1</mtd></mtr></mtable
            ></mfenced
          ></math
        >
      </td>
      <td colspan="1" rowspan="2">
        <math
          ><mfenced
            ><mtable
              ><mtr><mtd>cos(a)</mtd><mtd>-sin(a)</mtd><mtd>0</mtd></mtr
              ><mtr><mtd>sin(a)</mtd><mtd>cos(a)</mtd><mtd>0</mtd></mtr
              ><mtr><mtd>0</mtd><mtd>0</mtd><mtd>1</mtd></mtr></mtable
            ></mfenced
          ></math
        >
      </td>
      <td colspan="1" rowspan="2">
        <math
          ><mfenced
            ><mtable
              ><mtr
                ><mtd>cos(a)</mtd><mtd>-sin(a)</mtd><mtd>0</mtd
                ><mtd>0</mtd></mtr
              ><mtr
                ><mtd>sin(a)</mtd><mtd>cos(a)</mtd><mtd>0</mtd><mtd>0</mtd></mtr
              ><mtr><mtd>0</mtd><mtd>0</mtd><mtd>1</mtd><mtd>0</mtd></mtr
              ><mtr
                ><mtd>0</mtd><mtd>0</mtd><mtd>0</mtd><mtd>1</mtd></mtr
              ></mtable
            ></mfenced
          ></math
        >
      </td>
    </tr>
    <tr>
      <td><code>[cos(a) sin(a) -sin(a) cos(a) 0 0]</code></td>
    </tr>
  </tbody>
</table>

## Exemples

### Exemple simple

#### CSS

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.tourne {
  transform: rotate(45deg); /* Équivalent à rotateZ(45deg) */
  background-color: pink;
}
```

#### HTML

```html
<div>Normal</div>
<div class="tourne">Tourné</div>
```

#### Résultat

{{EmbedLiveSample("Exemple_simple", "auto", 180)}}

### Associer une rotation à une autre transformation

Lorsqu'on applique plusieurs transformations, il faut faire attention à l'ordre dans lequel elles sont appliquées. Ainsi, si on applique une rotation avant une translation, la translation se fera selon le nouvel axe de rotation !

#### CSS

```css
div {
  position: absolute;
  left: 40px;
  top: 40px;
  width: 100px;
  height: 100px;
  background-color: lightgray;
}

.rotate {
  background-color: transparent;
  outline: 2px dashed;
  transform: rotate(45deg);
}

.rotate-translate {
  background-color: pink;
  transform: rotate(45deg) translateX(180px);
}

.translate-rotate {
  background-color: gold;
  transform: translateX(180px) rotate(45deg);
}
```

#### HTML

```html
<div>Normal</div>
<div class="rotate">Tourné</div>
<div class="rotate-translate">Tourné puis translaté</div>
<div class="translate-rotate">Translaté puis tourné</div>
```

#### Résultat

{{EmbedLiveSample("Associer_une_rotation_avec_une_autre_transformation", "auto", 320)}}

## Spécifications

| Spécification                                                                                    | État                                 | Commentaires         |
| ------------------------------------------------------------------------------------------------ | ------------------------------------ | -------------------- |
| {{SpecName("CSS3 Transforms", "#funcdef-transform-rotate", "rotate()")}} | {{Spec2("CSS3 Transforms")}} | Définition initiale. |

## Compatibilité des navigateurs

Voir la page sur le type de donnée [`<transform-function>`](/fr/docs/Web/CSS/transform-function#compatibilité_des_navigateurs) pour les informations de compatibilité associées.

## Voir aussi

- {{cssxref("transform")}}
- {{cssxref("&lt;transform-function&gt;")}}
- [`rotate3d()`](</fr/docs/Web/CSS/transform-function/rotate3d()>)
