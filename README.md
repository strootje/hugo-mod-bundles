# Bundles

## Usage

This module automaticaly pulls `scss` and `ts` files from the assets directory.
Use the following naming scheme's:
- assets/styles/mod/bundles/_*_<head/body>_<start/end>.scss
- assets/scripts/mod/bundles/_*_<head/body>_<start/end>.ts

```html
<!DOCTYPE html>
<html lang="en">
	<head>
      <!-- ... -->
		{{- partial "bundle/head/end" . -}}
	</head>
	<body>
		{{- partial "bundle/body/start" . -}}

      <!-- ... -->

		{{- partial "bundle/body/end" . -}}
	</body>
</html>
```

## Installation
```bash
$ hugo mod get -u git.strooweb.nl/strooware/hugo-mod-bundles
```
