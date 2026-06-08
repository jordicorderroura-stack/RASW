# WebAR Switch NFT - reconocimiento por imagen

Esta demo usa AR.js con Natural Feature Tracking (NFT). No usa marcador HIRO.

## 1. Haz una buena foto del switch

Consejos:
- Foto frontal, sin inclinacion.
- Buena luz, sin reflejos.
- El switch debe ocupar casi toda la imagen.
- Mejor con textura: etiquetas, numeros, logos y puertos visibles.
- Si todos los switches son iguales, anade una etiqueta fisica visible como `SW-RACK-01` para diferenciarlos.
- Recomendado: imagen grande y nitida, idealmente 300 DPI o buena resolucion.

## 2. Genera los descriptores NFT

Usa el NFT Marker Creator Web:
https://carnaux.github.io/NFT-Marker-Creator/

Sube la foto del switch y genera los archivos. Debes obtener tres archivos:

- switch-01.fset
- switch-01.fset3
- switch-01.iset

Si salen con otro nombre, renombrarlos a `switch-01.*` o cambia en index.html esta linea:

url="descriptors/switch-01"

## 3. Copia los archivos

Pon los tres archivos dentro de la carpeta:

/descriptors/

Debe quedar asi:

/descriptors/switch-01.fset
/descriptors/switch-01.fset3
/descriptors/switch-01.iset
/index.html

## 4. Publica en HTTPS

La camara del movil requiere HTTPS. Opciones faciles:

- GitHub Pages
- Netlify
- Vercel

Tambien puedes probar localmente con un servidor HTTPS, pero para empezar es mas facil subirlo.

## 5. Ajusta las etiquetas

En index.html busca etiquetas como:

<a-text value="P1" position="-185 0 -18" ...>

Los numeros de `position` significan:

- Primer numero: izquierda/derecha.
- Segundo numero: altura sobre la imagen.
- Tercer numero: arriba/abajo dentro del frontal.

Ejemplo:

position="-185 0 -18"

Para varios switches, crea varios grupos de descriptor:

/descriptors/sw-rack-01.fset
/descriptors/sw-rack-01.fset3
/descriptors/sw-rack-01.iset
/descriptors/sw-rack-02.fset
/descriptors/sw-rack-02.fset3
/descriptors/sw-rack-02.iset

Luego duplica el bloque <a-nft> en index.html y cambia la URL.
