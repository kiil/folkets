---
title: Schema json

---


```json

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ClaimReview",
  "datePublished": "2016-06-22",
  "url": "http://example.com/news/science/worldisflat.html",
  "claimReviewed": "The world is flat",
  "itemReviewed": {
    "@type": "Claim",
    "author": {
      "@type": "Organization",
      "name": "Square World Society",
      "sameAs": "https://example.flatworlders.com/we-know-that-the-world-is-flat"
    },
    "datePublished": "2016-06-20",
    "appearance": {
      "@type": "OpinionNewsArticle",
      "url": "http://skeptical.example.net/news/a122121",
      "name": "Square Earth - Flat earthers for the Internet age",
      "datePublished": "2016-06-22",
      "author": {
        "@type": "Person",
        "name": "T. Tellar"
      }
    }
  },
  "author": {
    "@type": "Organization",
    "name": "Example.com science watch"
  },
  "reviewRating": {
    "@type": "Rating",
    "ratingValue": "1",
    "bestRating": "5",
    "worstRating": "1",
    "alternateName": "False"
  }
}
</script>

<script type="application/ld+json">
  {
    "@context" : "http://schema.org",
    "@type" : "ClaimReview",
    "author" :
    {
      "@type" : "Organization",
      "name" : "Mediemøllen",
      "url" : "https://www.folkets.dk/brands/mediemøllen"
    },
    "claimReviewed" : "Vi er på vej mod et klima, hvor havet igen kan stige med 13 meter",
    "datePublished" : "2019-10-11",
    "itemReviewed" :
    {
      "@type" : "Claim",
      "author" :
      {
        "@type" : "Organization",
        "name" : "Danmarks Radio"
      },
      "datePublished" : "2019-10-09",
      "firstAppearance" :
      {
        "@type" : "CreativeWork",
        "url" : "https://www.dr.dk/nyheder/viden/klima/det-er-sket-foer-vi-er-paa-vej-mod-et-klima-hvor-havet-igen-kan-stige-med-13"
      }
    },
    "reviewRating" :
    {
      "@type" : "Rating",
      "alternateName" : "Vildledende"
    },
    "url" : "https://www.folkets.dk/node/3762"
  }
</script>


```
