# Repertorio de Alabanza

App para el ministerio de alabanza: busca canciones del repertorio y guarda su tonalidad, tempo, compás, temas, letra y notas. También registra qué se cantó en cada servicio (domingos, miércoles y eventos especiales) y muestra qué canciones no se han cantado últimamente.

## Dos versiones, un mismo código

| | claude.ai | GitHub Pages |
|---|---|---|
| Dónde se guardan los datos | Base de datos compartida del artefacto | En el navegador de cada persona (`localStorage`) |
| Compartido entre dispositivos y equipo | Sí | No; usa **Descargar copia** / **Importar copia** |
| Recomendaciones | Con IA (Claude) | Búsqueda por palabras en títulos, temas y letras |

`index.html` detecta dónde se está ejecutando: si tiene la base de datos de claude.ai, la usa; si no, entra en modo independiente.

## Archivos

- `index.html`: la app completa en un solo archivo (HTML, CSS y JS, sin dependencias).
- `data/repertorio.json`: canciones y servicios precargados. En modo independiente se combinan con lo que ya hay en el navegador: entra lo nuevo y se actualiza lo que haya cambiado, pero no se recupera lo que borraste en ese navegador.
- `.nojekyll`: hace que GitHub Pages sirva los archivos tal cual.

## Formato de importación rápida

En **Servicios → Importar lista** puedes pegar:

```
Domingo 15/11/2026
1. Cuán grande es Él (G, 70)
2. Way Maker - Sinach - E

Miércoles 11/11
- Te doy gloria (A)
```

## Ver en local

```bash
python3 -m http.server 8000
```

Luego abre http://localhost:8000. Si abres `index.html` directamente como archivo no se cargan los datos precargados, porque el navegador bloquea esa lectura.
