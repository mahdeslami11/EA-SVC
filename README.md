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

Article of project:
[EA-SVC.pdf](https://github.com/yasihsni/EA-SVC/files/10368994/EA-SVC.pdf)

Abstract of article:
[Abstract of article.pdf](https://github.com/yasihsni/EA-SVC/files/10368996/Abstract.of.article.pdf)

Project summary:
[Project summary.pdf](https://github.com/yasihsni/EA-SVC/files/10369000/Project.summary.pdf)

Tables of article:
[Tables of article.pdf](https://github.com/yasihsni/EA-SVC/files/10369011/Tables.of.article.pdf)

Articles related to the project:

[207.pdf](https://github.com/yasihsni/EA-SVC/files/10369023/207.pdf)

[261.pdf](https://github.com/yasihsni/EA-SVC/files/10369024/261.pdf)

[2016_paper_297.pdf](https://github.com/yasihsni/EA-SVC/files/10369026/2016_paper_297.pdf)

[1033.pdf](https://github.com/yasihsni/EA-SVC/files/10369033/1033.pdf)

[2120_adagan_adaptive_gan_for_many_t.pdf](https://github.com/yasihsni/EA-SVC/files/10369034/2120_adagan_adaptive_gan_for_many_t.pdf)

[Interspeech_2019_paper.pdf](https://github.com/yasihsni/EA-SVC/files/10369040/Interspeech_2019_paper.pdf)

[Kameoka2018SLT12_published.pdf](https://github.com/yasihsni/EA-SVC/files/10369041/Kameoka2018SLT12_published.pdf)

[track2_2_Zhou.pdf](https://github.com/yasihsni/EA-SVC/files/10369046/track2_2_Zhou.pdf)

[zhao2018icassp.pdf](https://github.com/yasihsni/EA-SVC/files/10369047/zhao2018icassp.pdf)

[zhao2019taslp.pdf](https://github.com/yasihsni/EA-SVC/files/10369048/zhao2019taslp.pdf)

Abstracts of articles:
[Abstracts of articles.pdf](https://github.com/yasihsni/EA-SVC/files/10369055/Abstracts.of.articles.pdf)



