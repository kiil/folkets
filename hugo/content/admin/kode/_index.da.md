---
title: Snippets
---

## Tooltip enable

```js
<script>
jQuery(document).ready(function($) {
$('[data-toggle="tooltip"]').tooltip()
})
</script>
```

## tablesorter-sort

Add class

```js
<script type="text/javascript">
jQuery(document).ready(function($) {
$(".views-table").addClass("tablesorter");
});
</script>
```

</script>

### Sort

```js
<script type="text/javascript">
jQuery(document).ready(function($) {
 $(".views-table").tablesorter( {sortList: [[1,1]]} );
});
</script>
```

## Openers closer

### Premi Opener

```js
<script type="text/javascript">
	jQuery(document).ready(function($) {
if ($.cookie('abo')) {
    $('.premi').attr('style', 'display: block !important');
}
});
</script>
```
