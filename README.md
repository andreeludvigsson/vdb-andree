[README.md](https://github.com/user-attachments/files/34945396/README.md)
# vdb-andree### Hi, I'm  Andree Ludvigsson👋

I build **VDB**, a Swedish planning tool for single-family houses, from the first floor-plan sketch to electrical, plumbing and heating drawings.

#### What I work on

- **VDB:** draw and plan houses in one place. It covers floor plans, walls, doors and windows, furniture, electrical systems (consumer unit, outlets, switches, conduits), water and waste pipes, heating and rainwater, with a 3D view of the result.
- **Rekryt, VDB's own wall detector:** reads a scanned floor plan and proposes where the walls are, for the user to review. It is trained from scratch on openly licensed data (Swiss Dwellings by Archilyse AG, [CC BY 4.0](https://zenodo.org/records/7788422)) and VDB's own synthetic drawings.
- **The AI architect:** an assistant that turns plain Swedish ("flytta dörren mellan hallen och köket till x=4,2 y=3") into drawing edits. Every edit is simulated in the drawing engine and checked by rule-based reviewers before the user sees it, so the model never changes a drawing unchecked.

#### How I build AI

- **Open-weight models only** (currently Qwen3, Apache 2.0), running on our own machines, so customer drawings stay private.
- **Engine-verified self-training:** a larger teacher model proposes answers, and the drawing engine and a rule-based judge accept or reject them. Only verified answers become training data, which is then distilled into a small model that runs on a single consumer GPU.
- **Honest measurement:** a locked test split that is never trained on, and the same metrics for every model.

#### Current focus

Teaching the assistant to move objects, walls, doors, windows, conduits and pipes **to exact coordinates**, in fully equipped test houses (two floors, electrical, plumbing, heating, rainwater, furniture).

#### Tech

Python · PyTorch · ONNX · Hugging Face PEFT / LoRA · Ollama · FastAPI · React / Three.js · Kaggle

#### Contact

https://www.facebook.com/andree.ludvigsson.7
