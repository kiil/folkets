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

  <a href="/na/abonnement" role="button" class="btn btn-lg btn-danger btn-block">Se fordele</a>

  <div class="text-right text-muted small">
  Abonnent? <a class="loginlinkwithdestination" href="/user/login?destination=/node/3595">Log på og slip for besked</a>
  </div>
</div>
<!-- Vises overalt - husk cta button - slut -->



```

Vigtigt - da den kommer som popup skal der altid være mindst en fungerende button.
