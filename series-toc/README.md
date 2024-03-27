# Series Taxonomy TOC Shortcode

This module lets you group articles together under a 'series'.  
Adding the shortcode will display a TOC to navigate quickly between articles in a series.  
Inspiration came from the HUGO Blowfish theme.

## Install Module

Add the following code to your module list in the `config/_default/module.toml` file.

```toml
[[imports]]
path = "github.com/mbrejla/hugo-modules/series-toc"
```

Add the following code to your `assets/scss/custom.scss` file.

```scss
@import 'series-toc';
```

<hr>

## Set up your taxonomies

Add the `series` taxonomy to your site configuration.  
>While adding custom taxonomies, you need to put in the default taxonomies too, if you want to keep them.

```toml
[taxonomies]
  category = 'categories'
  tag = 'tags'
  series = 'series'
```

<hr>

## Use it in your articles

### Frontmatter

Add the following to your frontmatter:

```md
---
# Name of series
series: ["Name of series"]
# Part in series
series_order: 01
# Choose if module starts opened (default: false) 
series_open: true
---
```
### Article Body

Add this shortcode wherever you want the series-toc to appear in your article:

```md
{{< series-toc >}}
```

## Custom Styling

You can supply a custom class when calling the shortcode:

```md
{{< series-toc class="fancy">}}
```

which will result in a similar html output:

```html
<details class"series-table fancy>
  <summary>TOC Header</summary>
  <nav id="SeriesToc">
    <ul>
      <li>
        <a>First article in series</a>
      </li>
      ...
      <li>Current article</li>
      ...
    </ul>
  </nav>  
</details>

```

## Translation

The following strings are avaiable for i18n translation:

```i18n
"article_part_of_series" | default "This article is part of a series."
"article_part" | default "Part"
"article_this_article" | default "This article"
```