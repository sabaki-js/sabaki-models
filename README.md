# sabaki-models
Poids publics des modèles `mini` (minilaya ONNX) et `nano` (TF-IDF).
Les binaires sont dans les GitHub Releases (pas de LFS). Vérifiez le SHA256 (`SHA256SUMS`).
- `nano-tfidf/` : poids légers embarqués aussi dans les plugins npm (~1 Mo).
- `minilaya-onnx/` : ONNX fp32 par workflow (~87 Mo/modèle), téléchargés au premier usage.

## Generalist (`generalist` → `v1.0.0`)

- `generalist.onnx` : A0 fp32, 90,4 Mo (référence).
- `generalist_int8.onnx` : A0 quantifié dynamiquement QInt8 per-channel, 23,0 Mo.
  Mesuré sur 2 160 cas labellisés : **75,42 % vs 75,88 %** en fp32 (−0,46 pt),
  accord 93,5 %. Servi par le Worker edge (`sabaki-js/sabaki-worker`) et par
  l'origine pm2 depuis le 2026-10-20.

