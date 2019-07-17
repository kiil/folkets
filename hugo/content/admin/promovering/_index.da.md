---
title: Promovering

---

Omhandler promovering af FOLKETS eller brands på folkets - ikke eksterne brands.

Kapmagne kører under menu-bar, i pop-up og over site footer. Derudover har den sin egen side.

Da egen side kan deles, skal  kampagnen være egnet til deling, men samtid kort nok til at den  kan være i modal.

Kampagner er sat op i indholdstypen 'tekst' og med typen ""

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
<div class="p-3" markdown="1">
  Selve indholdet
</div>
<!-- Vises overalt - husk cta button - slut -->

```

Vigtigt - da den kommer som popup skal der altid være mindst en fungerende button.
