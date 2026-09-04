# lbcdsg

### Applied AI systems for reliable decisions and safer software

I build end-to-end systems across **computer vision**, **AI-assisted software
security**, and **developer tooling**. My work emphasizes reproducible
experiments, explicit evaluation protocols, and honest limitations—not only a
working demo.

I am preparing for graduate study in Hong Kong and am especially interested in
robust visual learning, trustworthy AI systems, and evaluation under real-world
constraints.

## Research interests

- **Computer vision:** detection and segmentation for industrial and
  infrastructure inspection, especially under class imbalance and domain shift.
- **Trustworthy AI:** leakage-aware evaluation, interpretable failure analysis,
  and clear boundaries between research prototypes and production claims.
- **AI systems:** combining learned components with deterministic, testable
  software and safety controls.

## Evidence at a glance

| Project | Research or engineering question | Method | Verifiable evidence |
|---|---|---|---|
| [Bottle Defect Detection](https://github.com/3196973848/bottle-defect-detection) | Can a two-stage system improve fine-grained detection of five visually similar pharmaceutical-bottle defects? | Class-agnostic YOLO26s proposals + dual-view ConvNeXt-Tiny classification and class-specific box refinement | Clean held-out test: **2,159 images / 2,222 boxes**, **98.07% Micro F1**, **95.16% Macro F1**, **97.17% exact-image accuracy**; frozen validation thresholds and documented leakage controls |
| [DeepCrack U-Net Segmentation](https://github.com/3196973848/deepcrack-unet-segmentation) | How well does a compact U-Net recover sparse road-crack pixels from limited data? | Aspect-ratio-preserving preprocessing, paired augmentation, U-Net, Dice + cross-entropy loss | Fixed **240 / 60 / 237** train-validation-test split; best validation Dice **0.8711**; independent-test Dice **0.6502**, IoU **0.4817** |
| [Wardrail](https://github.com/3196973848/wardrail) | How can AI-assisted developers catch security mistakes before code runs or reaches GitHub? | Local TypeScript static analysis, bounded Git-history scanning, short-range data-flow checks, SARIF and pre-commit integration | **17 explainable rules**; offline-by-default analysis; terminal, JSON and SARIF output; tested on Node.js 20, 22 and 24 |
| [Daybreak](https://github.com/3196973848/daybreak) | How can open-ended goals become feasible daily plans without making scheduling opaque? | LLM-based goal decomposition + deterministic duration-aware scheduler + task-scoped tutor | Local-first FastAPI/React/SQLite application with backend tests, frontend tests, CI builds and calendar export |

> Metrics above are project results, not peer-reviewed publication claims. Each
> repository documents its data boundary, evaluation protocol, and known
> limitations.

## Selected work

### Industrial visual inspection

The [bottle-defect project](https://github.com/3196973848/bottle-defect-detection)
is my most complete computer-vision study. It includes a model card, a frozen
post-processing configuration, per-class error analysis, downloadable weights
with SHA-256 checksums, and explicit warnings about normal-product false
positives and cross-line generalization.

### Segmentation from a limited dataset

[DeepCrack U-Net](https://github.com/3196973848/deepcrack-unet-segmentation)
covers the full experimental path from paired data validation to held-out test
evaluation and single-image inference. The gap between validation and test Dice
is reported directly because understanding that gap is part of the result.

### Safety for AI-assisted development

[Wardrail](https://github.com/3196973848/wardrail) explores trustworthy tooling
at the software boundary. It detects leaked credentials, unsafe agent
instructions, dangerous commands, and simple secret-to-network flows without
uploading source code or executing the scanned project.

## How I work

- Separate training, validation, and test decisions; freeze thresholds before
  final evaluation.
- Check for overlap and leakage, then document exclusions explicitly.
- Report per-class results and failure modes instead of relying on one headline
  metric.
- Pair experiments with reproducible commands, model cards, tests, CI, and
  release artifacts.
- State where evidence stops: a research result is not automatically a
  production guarantee.

## Tools

`Python` · `PyTorch` · `Ultralytics` · `TypeScript` · `Node.js` · `FastAPI` ·
`React` · `SQLite` · `GitHub Actions` · `SARIF`
