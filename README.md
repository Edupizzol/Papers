# Artigos

Artigos técnicos de Eduardo Jesus Dal Pizzol, estudante de Engenharia de Software na Universidade de Brasília (UnB/FCTE).

> Os dois artigos abaixo foram produzidos na disciplina FGA0261 — Inteligência Artificial II (UnB, 2026), em formato IEEE. São trabalhos acadêmicos **não revisados por pares**, e os resultados são exploratórios: nenhum dos modelos é indicado para uso clínico.

---

## 1. Comparação entre ResNet50 e EfficientNet-B0 na classificação de lesões dentárias em radiografias panorâmicas por transfer learning

**Autores:** Eduardo Jesus Dal Pizzol, Matheus Lemes Amaral · 2026
📄 [PDF](2026-lesoes-dentarias-resnet-efficientnet.pdf) · 💻 [Código](https://github.com/Edupizzol/odonto-cnn)

Compara duas CNNs pré-treinadas no ImageNet, ajustadas por fine-tuning, na classificação multirrótulo de cárie, cárie profunda e lesão periapical em 2.996 dentes do conjunto público DENTEX. O protocolo é idêntico para as duas redes, com três sementes e divisão por radiografia para evitar vazamento de dados.

- **Discriminação equivalente:** AUC macro de 0,856 (ResNet50) e 0,855 (EfficientNet-B0).
- **Calibração:** a EfficientNet-B0, com cerca de 6× menos parâmetros, teve perda logarítmica menor (0,362 contra 0,417; IC 95% da diferença [0,020; 0,092], por bootstrap).
- **Stack:** PyTorch, torchvision, CLAHE, bootstrap pareado.

---

## 2. Detecção de tumores cerebrais em imagens de ressonância magnética por transfer learning com validação cruzada por grupos

**Autores:** Matheus Lemes Amaral, Eduardo Jesus Dal Pizzol · 2026
📄 [PDF](2026-tumor-cerebral-rm-validacao-por-grupos.pdf) · 💻 [Código](LINK_DO_REPOSITORIO)

Classifica fatias de RM cerebral em "com tumor" e "sem tumor" em um conjunto público pequeno, com foco no protocolo para eliminar vazamento de dados. Foram removidas 25 cópias idênticas, as quase-duplicatas foram agrupadas por hash perceptual (216 grupos) e a avaliação usou validação cruzada estratificada por grupos (5 folds × 3 sementes).

- **Transfer learning vs. treino do zero:** a ResNet-18 pré-treinada atingiu AUC de 0,917 a 0,923 em validação cruzada, e no teste final teve AUC de 0,989 contra 0,733 da CNN treinada do zero.
- **Ajustes de treino:** nenhuma das configurações testadas (agendamento da taxa de aprendizado, weight decay, congelamento inicial) diferiu da inicial de forma significativa.
- **Limitação:** o teste tem só 34 imagens e não há identificação de paciente nem validação externa.
- **Stack:** PyTorch, torchvision, OpenCV, dHash, validação cruzada por grupos.

---

## Licença

Os textos dos artigos estão sob [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.pt-br). Os conjuntos de dados usados seguem as licenças dos seus autores (o DENTEX está sob CC BY-NC-SA 4.0).
