# RegaloNatural (Desarrollo)

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Dillinger is a cloud-enabled, mobile-ready, offline-storage, AngularJS powered HTML5 Markdown editor.

  - Type some Markdown on the left
  - See HTML in the right
  - Magic

# Ultimas modificaciones!

  [2019-04-27] -  ***03-Recoloca-Seleccion-Colores***: 
  
- Se ha reestructurado la página principal del producto para incluir los colores y otras características dentro del grupo de personalización.
  




### Detalle cambios

  [2019-04-27] -  ***03-Recoloca-Seleccion-Colores***: 
 Archivos modificados:
 
 |Ref| Archivo | Descripción |
| ------ | ------ | ------ |
|[001](####Ref-002)|\themes\leo_angel\templates\catalog\_partials\product-customization.tpl | Se incrusta en este archivo el bloque correspondiente a **produc-variants.tpl**|
|[002](###Detalle-cambios)|\themes\leo_angel\details\detail1519834497.tpl| Se anula la referencia a **produc-variants.tpl** dentro de la *class="product-actions"*|


##### Ref-001 \themes\leo_angel\templates\catalog_partials\product-customization.tpl
```tpl
...linea 24
<section class="product-customization">
  {if !$configuration.is_catalog}
    <div class="card card-block">
      <h3 class="h4 card-title">{l s='Product customization' d='Shop.Theme.Catalog'}</h3>
      {l s='Don\'t forget to save your customization to be able to add to cart' d='Shop.Forms.Help'}

      {block name='product_customization_form'}
        <form method="post" action="{$product.url}" enctype="multipart/form-data">
          <ul class="clearfix">
-->              {block name='product_variants'}
-->                  {include file='catalog/_partials/product-variants.tpl'}
-->              {/block}

              {foreach from=$customizations.fields item="field"}
              <li class="product-customization-item">
                <label> {$field.label}</label>

...linea 41
```
##### Ref-002 \themes\leo_angel\details\detail1519834497.tpl
```tpl
...linea 138
<div class="product-actions">
  {block name='product_buy'}
    <form action="{$urls.pages.cart}" method="post" id="add-to-cart-or-refresh">
      <input type="hidden" name="token" value="{$static_token}">
      <input type="hidden" name="id_product" value="{$product.id}" id="product_page_product_id">
      <input type="hidden" name="id_customization" value="{$product.id_customization}" id="product_customization_id">

-->        {* Anulado *}
--> {*     {block name='product_variants'}
-->        {include file='catalog/_partials/product-variants.tpl'}
-->      {/block}
-->*}
      {block name='product_pack'}
        {if $packItems}
          <section class="product-pack">

...linea 154
```

