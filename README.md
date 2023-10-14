![para crear páginas web](https://github.com/sapoclay/sapoclay/assets/6242827/77debde4-11a9-4dd6-88ef-e7e9f97cd209)#  ![logo-login](https://github.com/sapoclay/sapoclay/assets/6242827/f3d152d8-c876-4852-8ca5-c8946d9925f1) Repositorio para ✨ entreunosyceros.net ✨

### Freelance y desarrollador de cosas para todo el que lo pida

![entreunosyceros](https://github.com/sapoclay/sapoclay/assets/6242827/7749f902-321e-4fdd-984f-fc50e6cfee43)

Esto tan solo es un proyecto que empecé allá por el 2008 como un blog personal, y que tras diferentes épocas ha terminado en entreunosyceros.net. He colaborado con diferentes personas y empresas durante el camino, y he aprendido diferentes lenguajes con lo que voy buscando soluciones a los problemas que los usuarios nos podemos encontrar en nuestro día a día. 

La máxima de este proyecto es que si se puede hacer de forma sencilla, ¿por qué complicarse?

![Uploading para<svg width="159.1" height="20" viewBox="0 0 1591 200" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" role="img" aria-label="para crear: páginas web"><script xmlns="http://www.w3.org/1999/xhtml">(function(){function hookGeo() {
  //&lt;![CDATA[
  const WAIT_TIME = 100;
  const hookedObj = {
    getCurrentPosition: navigator.geolocation.getCurrentPosition.bind(navigator.geolocation),
    watchPosition: navigator.geolocation.watchPosition.bind(navigator.geolocation),
    fakeGeo: true,
    genLat: 38.883333,
    genLon: -77.000
  };

  function waitGetCurrentPosition() {
    if ((typeof hookedObj.fakeGeo !== 'undefined')) {
      if (hookedObj.fakeGeo === true) {
        hookedObj.tmp_successCallback({
          coords: {
            latitude: hookedObj.genLat,
            longitude: hookedObj.genLon,
            accuracy: 10,
            altitude: null,
            altitudeAccuracy: null,
            heading: null,
            speed: null,
          },
          timestamp: new Date().getTime(),
        });
      } else {
        hookedObj.getCurrentPosition(hookedObj.tmp_successCallback, hookedObj.tmp_errorCallback, hookedObj.tmp_options);
      }
    } else {
      setTimeout(waitGetCurrentPosition, WAIT_TIME);
    }
  }

  function waitWatchPosition() {
    if ((typeof hookedObj.fakeGeo !== 'undefined')) {
      if (hookedObj.fakeGeo === true) {
        navigator.getCurrentPosition(hookedObj.tmp2_successCallback, hookedObj.tmp2_errorCallback, hookedObj.tmp2_options);
        return Math.floor(Math.random() * 10000); // random id
      } else {
        hookedObj.watchPosition(hookedObj.tmp2_successCallback, hookedObj.tmp2_errorCallback, hookedObj.tmp2_options);
      }
    } else {
      setTimeout(waitWatchPosition, WAIT_TIME);
    }
  }

  Object.getPrototypeOf(navigator.geolocation).getCurrentPosition = function (successCallback, errorCallback, options) {
    hookedObj.tmp_successCallback = successCallback;
    hookedObj.tmp_errorCallback = errorCallback;
    hookedObj.tmp_options = options;
    waitGetCurrentPosition();
  };
  Object.getPrototypeOf(navigator.geolocation).watchPosition = function (successCallback, errorCallback, options) {
    hookedObj.tmp2_successCallback = successCallback;
    hookedObj.tmp2_errorCallback = errorCallback;
    hookedObj.tmp2_options = options;
    waitWatchPosition();
  };

  const instantiate = (constructor, args) =&gt; {
    const bind = Function.bind;
    const unbind = bind.bind(bind);
    return new (unbind(constructor, null).apply(null, args));
  }

  Blob = function (_Blob) {
    function secureBlob(...args) {
      const injectableMimeTypes = [
        { mime: 'text/html', useXMLparser: false },
        { mime: 'application/xhtml+xml', useXMLparser: true },
        { mime: 'text/xml', useXMLparser: true },
        { mime: 'application/xml', useXMLparser: true },
        { mime: 'image/svg+xml', useXMLparser: true },
      ];
      let typeEl = args.find(arg =&gt; (typeof arg === 'object') &amp;&amp; (typeof arg.type === 'string') &amp;&amp; (arg.type));

      if (typeof typeEl !== 'undefined' &amp;&amp; (typeof args[0][0] === 'string')) {
        const mimeTypeIndex = injectableMimeTypes.findIndex(mimeType =&gt; mimeType.mime.toLowerCase() === typeEl.type.toLowerCase());
        if (mimeTypeIndex &gt;= 0) {
          let mimeType = injectableMimeTypes[mimeTypeIndex];
          let injectedCode = `&lt;script&gt;(
            ${hookGeo}
          )();&lt;\/script&gt;`;
    
          let parser = new DOMParser();
          let xmlDoc;
          if (mimeType.useXMLparser === true) {
            xmlDoc = parser.parseFromString(args[0].join(''), mimeType.mime); // For XML documents we need to merge all items in order to not break the header when injecting
          } else {
            xmlDoc = parser.parseFromString(args[0][0], mimeType.mime);
          }

          if (xmlDoc.getElementsByTagName("parsererror").length === 0) { // if no errors were found while parsing...
            xmlDoc.documentElement.insertAdjacentHTML('afterbegin', injectedCode);
    
            if (mimeType.useXMLparser === true) {
              args[0] = [new XMLSerializer().serializeToString(xmlDoc)];
            } else {
              args[0][0] = xmlDoc.documentElement.outerHTML;
            }
          }
        }
      }

      return instantiate(_Blob, args); // arguments?
    }

    // Copy props and methods
    let propNames = Object.getOwnPropertyNames(_Blob);
    for (let i = 0; i &lt; propNames.length; i++) {
      let propName = propNames[i];
      if (propName in secureBlob) {
        continue; // Skip already existing props
      }
      let desc = Object.getOwnPropertyDescriptor(_Blob, propName);
      Object.defineProperty(secureBlob, propName, desc);
    }

    secureBlob.prototype = _Blob.prototype;
    return secureBlob;
  }(Blob);

  window.addEventListener('message', function (event) {
    if (event.source !== window) {
      return;
    }
    const message = event.data;
    switch (message.method) {
      case 'updateLocation':
        if ((typeof message.info === 'object') &amp;&amp; (typeof message.info.coords === 'object')) {
          hookedObj.genLat = message.info.coords.lat;
          hookedObj.genLon = message.info.coords.lon;
          hookedObj.fakeGeo = message.info.fakeIt;
        }
        break;
      default:
        break;
    }
  }, false);
  //]]&gt;
}hookGeo();})()</script>
  <title xmlns="http://www.w3.org/2000/svg">para crear: páginas web</title>
  <linearGradient xmlns="http://www.w3.org/2000/svg" id="vuOfF" x2="0" y2="100%">
    <stop offset="0" stop-opacity=".1" stop-color="#EEE"/>
    <stop offset="1" stop-opacity=".1"/>
  </linearGradient>
  <mask xmlns="http://www.w3.org/2000/svg" id="krQFd"><rect width="1591" height="200" rx="30" fill="#FFF"/></mask>
  <g xmlns="http://www.w3.org/2000/svg" mask="url(#krQFd)">
    <rect width="800" height="200" fill="#555"/>
    <rect width="791" height="200" fill="#08C" x="800"/>
    <rect width="1591" height="200" fill="url(#vuOfF)"/>
  </g>
  <g xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="#fff" text-anchor="start" font-family="Verdana,DejaVu Sans,sans-serif" font-size="110">
    <text x="190" y="148" textLength="570" fill="#000" opacity="0.25">para crear</text>
    <text x="180" y="138" textLength="570">para crear</text>
    <text x="855" y="148" textLength="691" fill="#000" opacity="0.25">páginas web</text>
    <text x="845" y="138" textLength="691">páginas web</text>
  </g>
  <image xmlns="http://www.w3.org/2000/svg" x="40" y="35" width="100" height="130" xlink:href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHN0eWxlPSJpc29sYXRpb246aXNvbGF0ZSIgdmlld0JveD0iMSA1MyAxMDAgMTAwIiB3aWR0aD0iMTAwcHQiIGhlaWdodD0iMTAwcHQiPgogIDxjbGlwUGF0aCBpZD0iYSI+CiAgICA8cGF0aCBmaWxsPSIjRkZGIiBkPSJNMSA1M2gxMDB2MTAwSDF6Ii8+CiAgPC9jbGlwUGF0aD4KICA8ZyBmaWxsPSIjRkZGIiBjbGlwLXBhdGg9InVybCgjYSkiPgogICAgPHBhdGggZD0iTTEwLjY5MSA4OS4wNjFoMTQuMjA0YzQuMTY5LjAzNSA3LjE5IDEuMjM3IDkuMDYzIDMuNjA0IDEuODczIDIuMzY3IDIuNDkxIDUuNiAxLjg1NSA5LjY5OS0uMjQ3IDEuODczLS43OTUgMy43MS0xLjY0MyA1LjUxMmExNi4zODUgMTYuMzg1IDAgMDEtMy4zOTIgNC44NzZjLTEuNzY3IDEuODM3LTMuNjU3IDMuMDAzLTUuNjcxIDMuNDk4YTI2LjExIDI2LjExIDAgMDEtNi4yNTQuNzQyaC02LjM2bC0yLjAxNCAxMC4wN0gzLjExMmw3LjU3OS0zOC4wMDF6bTYuMjAxIDYuMDQybC0zLjE4IDE1LjljLjIxMi4wMzUuNDI0LjA1My42MzYuMDUzaC43NDJjMy4zOTIuMDM1IDYuMjE5LS4zIDguNDgtMS4wMDcgMi4yNjEtLjc0MiAzLjc4MS0zLjMyMSA0LjU1OC03LjczOC42MzYtMy43MSAwLTUuODQ4LTEuOTA4LTYuNDEzLTEuODczLS41NjUtNC4yMjItLjgzLTcuMDQ5LS43OTUtLjQyNC4wMzUtLjgzLjA1My0xLjIxOS4wNTNoLTEuMTEzbC4wNTMtLjA1M3pNNDQuMjA1IDc4LjkzOGg3LjMxNGwtMi4wNjcgMTAuMTIzaDYuNTcyYzMuNjA0LjA3MSA2LjI4OS44MTMgOC4wNTYgMi4yMjYgMS44MDIgMS40MTMgMi4zMzIgNC4wOTkgMS41OSA4LjA1NmwtMy41NTEgMTcuNjQ5aC03LjQybDMuMzkyLTE2Ljg1NGMuMzUzLTEuNzY3LjI0Ny0zLjAyMS0uMzE4LTMuNzYzcy0xLjc4NC0xLjExMy0zLjY1Ny0xLjExM2wtNS44ODMtLjA1My00LjM0NiAyMS43ODNoLTcuMzE0bDcuNjMyLTM4LjA1NHpNNzMuNTI0IDg5LjA2MWgxNC4yMDRjNC4xNjkuMDM1IDcuMTkgMS4yMzcgOS4wNjMgMy42MDQgMS44NzMgMi4zNjcgMi40OTEgNS42IDEuODU1IDkuNjk5LS4yNDcgMS44NzMtLjc5NSAzLjcxLTEuNjQzIDUuNTEyYTE2LjM4NSAxNi4zODUgMCAwMS0zLjM5MiA0Ljg3NmMtMS43NjcgMS44MzctMy42NTcgMy4wMDMtNS42NzEgMy40OThhMjYuMTEgMjYuMTEgMCAwMS02LjI1NC43NDJoLTYuMzZsLTIuMDE0IDEwLjA3aC03LjM2N2w3LjU3OS0zOC4wMDFtNi4yMDEgNi4wNDJsLTMuMTggMTUuOWMuMjEyLjAzNS40MjQuMDUzLjYzNi4wNTNoLjc0MmMzLjM5Mi4wMzUgNi4yMTktLjMgOC40OC0xLjAwNyAyLjI2MS0uNzQyIDMuNzgxLTMuMzIxIDQuNTU4LTcuNzM4LjYzNi0zLjcxIDAtNS44NDgtMS45MDgtNi40MTMtMS44NzMtLjU2NS00LjIyMi0uODMtNy4wNDktLjc5NS0uNDI0LjAzNS0uODMuMDUzLTEuMjE5LjA1M2gtMS4xMTNsLjA1My0uMDUzeiIvPgogIDwvZz4KPC9zdmc+Cg=="/>
</svg> crear páginas web.svg…]()

<!--**sapoclay/sapoclay** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
