---
title: Promovering

---

Omhandler promovering af FOLKETS eller brands på folkets - ikke eksterne brands.

Kapmagne kører i blocks der kun vises til anon under menu-bar, i pop-up og over site footer. Derudover har den sin egen side. Og endelig køre den som opfordringen ved paywall (via et embedded view)

```html
[views:embed:partnere:embed_1]
```

Da egen side kan deles, skal  kampagnen være egnet til deling, men samtid kort nok til at den  kan være i modal.

Kampagner er sat op i indholdstypen 'tekst' og med typen taksonomitypen 'Modal'. Findes også samlet her [/promovering](https://www.folkets.dk/promovering).

Template til body / brødtekst:

```html

<!-- Vises kun i modal start -->
<div class="modal-header">
  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
    <span aria-hidden="true">×</span>
  </button>
</div>
<!-- Vises kun i modal slut -->



<!-- Vises overalt - husk cta button - start -->



<div class="modal-body" markdown="1">
  Selve
  indholdet
  her

  <a href="/na/abonnement" role="button" class="btn btn-lg btn-logo-red btn-block">Se fordele</a>

  <div class="text-right text-muted small">
  Abonnent? <a class="loginlinkwithdestination" href="/user/login?destination=/node/3595">Log på og slip for besked</a>
  </div>
</div>



<!-- Vises overalt - husk cta button - slut -->



```

Vigtigt - da den kommer som popup skal der altid være mindst en fungerende button.

Definer bg-color og color kontekstuelt som klasser på blocks eller rundt om embed.

Eksempel:

```html

<!-- Vises kun i modal start -->
<div class="modal-header">
  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
    <span aria-hidden="true">×</span>
  </button>
</div>
<!-- Vises kun i modal slut -->




<!-- Vises overalt - husk cta button - start -->



<div class="modal-body" markdown="1">
  <p>Vi skal bruge <span class="display-1">[views:embed:guld_brugere:embed_4]</span> betalende brugere mere for at "breake even" - vil du være en af dem?</p>

  <hr class="my-3 border-top border-dark">
  <p class="lead"><span class="brand-folkets">FOLKETS</span> kan kun eksistere i kraft af direkte opbakning fra brugerne</p>
  <a class="btn btn-logo-red btn-lg out-content-goal-source" href="/na/abonnement" role="button">Se hvordan DU hjælper</a>



  <div class="text-right text-muted small">
  Abonnent? <a class="loginlinkwithdestination" href="/user/login?destination=/node/3595">Log på og slip for besked</a>
  </div>
</div>



<!-- Vises overalt - husk cta button - slut -->







<script type="text/javascript">
jQuery(document).ready(function($) {

$('.counter').each(function() {
  var $this = $(this),
      countTo = 400 - $this.attr('data-count');

  $({ countNum: $this.text()}).animate({
    countNum: countTo
  },

  {

    duration: 3000,
    easing:'swing',
    step: function() {
      $this.text(Math.floor(this.countNum));
    },
    complete: function() {
      $this.text(this.countNum);
      //alert('finished');
    }

  });  

  });

});
</script>



```
