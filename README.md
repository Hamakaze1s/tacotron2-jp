

## How to use
1. Put raw Japanese texts in ./filelists
2. Put WAV files in ./wav
3. Download NVIDIA's [pretrained model](https://drive.google.com/file/d/1c5ZTuT7J08wLUoVZ2KkUs_VdZuJ86ZqA/view?usp=sharing)
4. Open ./train.ipynb to start training
5. Download NVIDIA's [WaveGlow model](https://drive.google.com/open?id=1rpK8CzAAirq9sWZhe9nlfvxMF1dRgFbF)
6. Open ./inference.ipynb to generate voice

## Cleaners
File ./hparams.py line 30
### 1. 'japanese_cleaners'
#### Before
もし映画を見るなら、その後はカフェでゆっくりする方がいいかもしれません
#### After
moshieegaomirunara,sonogowakafedeyuclkurisuruhoogaiikamoshiremaseN.
### 2. 'japanese_tokenization_cleaners'
#### Before
もし映画を見るなら、その後はカフェでゆっくりする方がいいかもしれません
#### After
moshi eiga o miru nara, sonogo wa kafe de yuclkuri suru hoo ga ii kamo shire mase N.
### 3. 'japanese_accent_cleaners'
#### Before
もし映画を見るなら、その後はカフェでゆっくりする方がいいかもしれません
#### After
:mo)shi e(egao mi)runara,:so(nogowa ka)fede yu(clku)ri su(ru ho)oga i)ikamo shi(remase)N.

## Models
Remember to change this line in ./inference.ipynb
```python
sequence = np.array(text_to_sequence(text, ['japanese_cleaners']))[None, :]
```

#### Ayachi NeNe
* [Model 1](https://drive.google.com/file/d/1K9cLGUPopTeV0Nm25AvPHiTzxTQ2nEd3/view?usp=sharing) ['japanese_cleaners']
* [Model 2](https://drive.google.com/file/d/1iGjniqDoZEogmeyXi3wCE9cPFZsnHG_0/view?usp=sharing) ['japanese_tokenization_cleaners']
* [Model 3](https://sjtueducn-my.sharepoint.com/:u:/g/personal/cjang_cjengh_sjtu_edu_cn/Eb0WROtOsYBInTmQQZHf36IBSXmyVd4JiCF7OnQjOZkjGg?e=qbbsv4) ['japanese_accent_cleaners']


Reference: [NVIDIA/tacotron2](https://github.com/NVIDIA/tacotron2)
