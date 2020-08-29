---
title: Promovering

---


## Onsite campaigns


- campaign-modal
- campaign-paywall
- campaign-postcontent
- campaign-top ("topscroll")

Just links a tag manager med unik id per side. Navn er id - fx id=campaign-modal

Event-kategori: campaign  
Event-handling: Click Id
Event-label: Page Url



## Værktøjer til onsite campaigns

### campaign-postcontent

```html

<style>
body.content-paywall-truncated div.campaign-postcontent-wrapper {display:none;}
</style>

<div class="campaign-postcontent-wrapper">

<p>Du har læst et indlæg på Folkets.</p>

<p>Uden støtte ville vi ikke kunne bringe det.</p>

<h3><a href="/na/abonnement" id="campaign-postcontent" class="btn btn-lg btn-logo-red btn-block btn-danger">Se fordele</a></h3>

</div>

```


### campaign-modal

Baseret på boostrap modal

```html

<div class="modal fade" id="myCampaignModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true" data-backdrop="static" data-keyboard="false">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="cancel-modal close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true" class="cancel-modal">×</span>
        </button>
      </div>

      <div class="modal-body">

        <h4>Bak op om Danmarks uafhængige medier!</h4>

        <p>På Folkets har en række frie medier hjemme – medier som vel at mærke kun overlever takket være læsere som bidrager via medlemskab eller sponsorat.

          <p>Måske er det noget for dig?</p>

          <h3><a href="/na/abonnement" id="campaign-modal" class="btn btn-lg btn-logo-red btn-block btn-danger">Se fordele</a></h3>

      </div>

      <div class="modal-footer text-right text-muted small">
        <p class="mb-0">Abonnent? <a class="loginlinkwithdestination" href="/user/login?destination=/node/3595">Log direkte på</a></p>
      </div>

    </div>
  </div>
</div>


<script>
  jQuery(document).ready(function($) {

      setTimeout(function() {

        $('#myCampaignModal').modal('show');

      }, 32000);

  });
</script>

```




```






## Udfaset


Omhandler promovering af FOLKETS eller brands på folkets - ikke eksterne brands.

Kapmagne kører i blocks der kun vises til anon under menu-bar, i pop-up og over site footer. Derudover har den sin egen side. Og endelig køre den som opfordringen ved paywall (via et embedded view)

```html
[views:embed:partnere:embed_1]
```

Da egen side kan deles, skal  kampagnen være egnet til deling, men samtid kort nok til at den  kan være i modal.

Kampagner er sat op i indholdstypen 'tekst' og med typen taksonomitypen 'Promovering'. Findes også samlet her [/promovering](https://www.folkets.dk/promovering).

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

  <a href="/na/abonnement" role="button" class="btn btn-lg btn-danger btn-logo-red btn-block">Se fordele</a>

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
  <a class="btn btn-logo-red btn-danger btn-lg out-content-goal-source" href="/na/abonnement" role="button">Se hvordan DU hjælper</a>



  <div class="text-right text-muted small">
  Abonnent? <a class="loginlinkwithdestination" href="/user/login?destination=/node/3595">Log på og slip for besked</a>
  </div>
</div>



<!-- Vises overalt - husk cta button - slut -->









```
