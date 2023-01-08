# EA-SVC
An implement of "Phonetic Posteriorgrams based Many-to-Many Singing Voice Conversion via Adversarial Training"

## Data prepare
1. PPG features (10ms frameshift)
2. F0 features (10ms frameshift)
3. Speaker embedding (One embedding per wav file)
4. Audio files (wave format, 24000 sample rate, mono)

## Write Configuration
Set path / directory or other configurations in .json files in directory "configs"
Rewrite your data load function in utils/dataset.py

## Model Training

Single GPU
```bash
CUDA_VISIBLE_DEVICES=0 python train.py -c configs/stage1.json
CUDA_VISIBLE_DEVICES=0 python train.py -c configs/stage2.json
CUDA_VISIBLE_DEVICES=0 python train.py -c configs/stage3.json
```
This project describes an end-to-end adversarial singing voice conversion (EA-SVC) approach. It can directly generate
arbitrary singing waveform by given phonetic posterior- gram (PPG) representing content, F0 representing pitch, and
speaker embedding representing timbre, respectively. Pro- posed system is composed of three modules: generator G, the
audio generation discriminator DA, and the feature disentan- glement discriminator DF . The generator G encodes the features in parallel and inversely transforms them into the target waveform. In order to make timbre conversion more stable
and controllable, speaker embedding is further decomposed to the weighted sum of a group of trainable vectors
represent- ing different timbre clusters. Further, to realize more robust and accurate singing conversion, disentanglement
discrimina- torDF isproposedtoremovepitchandtimbrerelatedinformation that remains in the encoded PPG. Finally, a two-stage training is conducted to keep a stable and effective adversarial training process. Subjective evaluation results demonstrate the effectiveness of our proposed methods. Proposed
system outperforms conventional cascade approach and the WaveNet based end-to-end approach in terms of both singing
quality and singer similarity. Further objective analysis reveals that the model trained with the proposed two-stage
training strat- egy can produce a smoother and sharper formant which leads to higher audio quality.
