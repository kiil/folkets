---
title: Snippets
---





## Countdown


```html
<span id="days"></span> <span id="hours"></span> <span id="minutes"></span> <span id="seconds"></span>
```

```js
<script type="text/javascript">

function countdown(endDate) {
  let days, hours, minutes, seconds;

  endDate = new Date(endDate).getTime();

  if (isNaN(endDate)) {
    return;
  }

  setInterval(calculate, 1000);

  function calculate() {
    let startDate = new Date();
    startDate = startDate.getTime();

    let timeRemaining = parseInt((endDate - startDate) / 1000);

    if (timeRemaining >= 0) {
      days = parseInt(timeRemaining / 86400);
      timeRemaining = (timeRemaining % 86400);

      hours = parseInt(timeRemaining / 3600);
      timeRemaining = (timeRemaining % 3600);

      minutes = parseInt(timeRemaining / 60);
      timeRemaining = (timeRemaining % 60);

      seconds = parseInt(timeRemaining);

      document.getElementById("days").innerHTML = parseInt(days, 10);
      document.getElementById("hours").innerHTML = ("0" + hours).slice(-2);
      document.getElementById("minutes").innerHTML = ("0" + minutes).slice(-2);
      document.getElementById("seconds").innerHTML = ("0" + seconds).slice(-2);
    } else {
      return;
    }
  }
}

(function() {
  countdown('08/05/2019 05:00:00 PM');
}());

</script>
```

## simpel tæller

```html
<p class="counter" data-count=some-number>0</p>

```

```js
<script type="text/javascript">
jQuery(document).ready(function($) {

$('.counter').each(function() {
  var $this = $(this),
      // 400 can be changed or removed if just value shopwn or different count internval
      countTo = 400 - $this.attr('data-count');

  $({ countNum: $this.text()}).animate({
    countNum: countTo
  },

  {

    duration: 8000,
    easing:'linear',
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

## Openers closers

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

### Abon opener

```js
<script type="text/javascript">
	jQuery(document).ready(function($) {
if ($.cookie('abo')) {
    $('.abon').attr('style', 'display: block !important');
}
});
</script>
```

## Oui

### Oui source

```js
<script type="text/javascript">

(function(root, factory) {
  if (typeof define === 'function' && define.amd) {
    define(factory);
  } else if (typeof exports === 'object') {
    module.exports = factory(require,exports,module);
  } else {
    root.ouibounce = factory();
  }
}(this, function(require,exports,module) {

return function ouibounce(el, config) {
  var config     = config || {},
    aggressive   = config.aggressive || false,
    sensitivity  = setDefault(config.sensitivity, 20),
    timer        = setDefault(config.timer, 1000),
    delay        = setDefault(config.delay, 0),
    callback     = config.callback || function() {},
    cookieExpire = setDefaultCookieExpire(config.cookieExpire) || '',
    cookieDomain = config.cookieDomain ? ';domain=' + config.cookieDomain : '',
    cookieName   = config.cookieName ? config.cookieName : 'viewedOuibounceModal',
    sitewide     = config.sitewide === true ? ';path=/' : '',
    _delayTimer  = null,
    _html        = document.documentElement;

  function setDefault(_property, _default) {
    return typeof _property === 'undefined' ? _default : _property;
  }

  function setDefaultCookieExpire(days) {
    // transform days to milliseconds
    var ms = days*24*60*60*1000;

    var date = new Date();
    date.setTime(date.getTime() + ms);

    return "; expires=" + date.toUTCString();
  }

  setTimeout(attachOuiBounce, timer);
  function attachOuiBounce() {
    _html.addEventListener('mouseleave', handleMouseleave);
    _html.addEventListener('mouseenter', handleMouseenter);
    _html.addEventListener('keydown', handleKeydown);
  }

  function handleMouseleave(e) {
    if (e.clientY > sensitivity || (checkCookieValue(cookieName, 'true') && !aggressive)) return;

    _delayTimer = setTimeout(_fireAndCallback, delay);
  }

  function handleMouseenter(e) {
    if (_delayTimer) {
      clearTimeout(_delayTimer);
      _delayTimer = null;
    }
  }

  var disableKeydown = false;
  function handleKeydown(e) {
    if (disableKeydown || checkCookieValue(cookieName, 'true') && !aggressive) return;
    else if(!e.metaKey || e.keyCode !== 76) return;

    disableKeydown = true;
    _delayTimer = setTimeout(_fireAndCallback, delay);
  }

  function checkCookieValue(cookieName, value) {
    return parseCookies()[cookieName] === value;
  }

  function parseCookies() {
    // cookies are separated by '; '
    var cookies = document.cookie.split('; ');

    var ret = {};
    for (var i = cookies.length - 1; i >= 0; i--) {
      var el = cookies[i].split('=');
      ret[el[0]] = el[1];
    }
    return ret;
  }

  function _fireAndCallback() {
    fire();
    callback();
  }

  function fire() {
    // You can use ouibounce without passing an element
    // https://github.com/carlsednaoui/ouibounce/issues/30
    if (el) el.style.display = 'block';
    disable();
  }

  function disable(options) {
    var options = options || {};

    // you can pass a specific cookie expiration when using the OuiBounce API
    // ex: _ouiBounce.disable({ cookieExpire: 5 });
    if (typeof options.cookieExpire !== 'undefined') {
      cookieExpire = setDefaultCookieExpire(options.cookieExpire);
    }

    // you can pass use sitewide cookies too
    // ex: _ouiBounce.disable({ cookieExpire: 5, sitewide: true });
    if (options.sitewide === true) {
      sitewide = ';path=/';
    }

    // you can pass a domain string when the cookie should be read subdomain-wise
    // ex: _ouiBounce.disable({ cookieDomain: '.example.com' });
    if (typeof options.cookieDomain !== 'undefined') {
      cookieDomain = ';domain=' + options.cookieDomain;
    }

    if (typeof options.cookieName !== 'undefined') {
      cookieName = options.cookieName;
    }

    document.cookie = cookieName + '=true' + cookieExpire + cookieDomain + sitewide;

    // remove listeners
    _html.removeEventListener('mouseleave', handleMouseleave);
    _html.removeEventListener('mouseenter', handleMouseenter);
    _html.removeEventListener('keydown', handleKeydown);
  }

  return {
    fire: fire,
    disable: disable
  };
}
;

}));

</script>
```

### Oui call

```js
<script>

	jQuery(document).ready(function($) {


if (!$.cookie('abo')) {


      // if you want to use the 'fire' or 'disable' fn,
      // you need to save OuiBounce to an object
      var _ouibounce = ouibounce(document.getElementById('ouibounce-modal'), {
        aggressive: false,
        timer: 2000,
        callback: function() { console.log('ouibounce fired!'); }
      });

      $('body').on('click', function() {
        $('#ouibounce-modal').hide();
      });

      $('#ouibounce-modal .modal-footer').on('click', function() {
        $('#ouibounce-modal').hide();
      });

      $('#ouibounce-modal .modal-ouibounce').on('click', function(e) {
        e.stopPropagation();
      });

}

});

    </script>
```

### Oui modal

```html
<div id="ouibounce-modal">
  <div class="underlay"></div>
  <div class="modal-ouibounce">
    <div class="modal-title">
      <h4>Tak fordi De læste Folkets Avis</h4>
    </div>
    <div class="modal-body">
      <div class="row">
        <div class="col-sm-8">
          <p>Vi anbefaler et abonnement på avisen, så De</p>
          <ul>
            <li>slipper for reklamer og popups som denne</li>
            <li>får adgang til alle artikler, også journalistiske</li>
            <li>får komplet fritekstsøgning i hele arkivet</li>
            <li>får mulighed for daglige notifikationer</li>
            <li>får mulighed for ugentligt nyhedsbrev</li>
            <li>er med til at sikre mediets overlevelse</li>
          </ul>
          <p>Det koster kun 2 kroner om dagen.</p>
        </div>
        <div class="col-sm-4 alert-info alert">
          <p>Danmarks uafhængige medie</p>
          <p class="small">Vi får ikke mediestøtte, og De finder hos os en grundlæggende kritik af systemet, som mangler i andre aviser.</p>
        </div>
      </div>
      <div class="row">
        <div class="col-sm-12">
         <p class="text-center" style="margin-top: 2em;"><a class="btn btn-danger btn-primary btn-lg" href="/abonnement" role="button">Ja, tak – opret mig som abonnent!</a></p>
        </div>
      </div>
    </div>
  </div>
</div>
```
