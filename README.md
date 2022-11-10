#### SKL_KoreanSTT
### 한국어 STT 모델 개발 
해당 프로젝트는 한국어 음성인식 toolkit인 [kospeech](https://github.com/sooftware/kospeech)를 활용하여 개발하였습니다. 

## Data

* 한국어 STT(Speech-to-Text) 모델을 만들기 위해서 데이터는 크게 2가지로, 음성데이터와 해당 음성데이터의 전사데이터(행당 음성의 내용이 적힌 텍스트)가 있습니다.
* 음성데이터와 전사데이터는 AIHUB에서 제공하는 [한국인 대화 음성의 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=130) 중 
broadcast_01 폴더와 life_09 폴더에서 각각 5만개씩의 데이터, 총 10만개의 데이터를 활용하여 음성인식 모델을 학습시켰습니다.
* 음성인식 모델의 학습 준비에 필요한 단어사전(전사 데이터 이용), 단어사전을 바탕으로 한 정답 벡터화 하기 위해서는 전사데이터를 전처리하는 과정이 필요한데,
kospeech에서 제공하는 3가지 전처리 방식 중 character-unit 방식을 통해 문장의 전처리를 진행했습니다. 

# Output-Unit

* kospeech에서 제공하는 전처리 방식 

1. Character-Unit
`아 모 몬 소리야 칠 십 퍼센트 확률이라니`

2. Subword-Unit
`▁아 ▁모 ▁ 몬 ▁소리 야 ▁ 칠 ▁ 십 ▁퍼 센트 ▁확 률 이라 니`

3. Grapheme-Unit
`ㅇㅏ ㅁㅗ ㅁㅗㄴ ㅅㅗㄹㅣㅇㅑ ㅊㅣㄹ ㅅㅣㅂ ㅍㅓㅅㅔㄴㅌㅡ ㅎㅘㄱㄹㅠㄹㅇㅣㄹㅏㄴㅣ`

* 위의 전처리 방식들은 문장을 토큰화(문장을 최소 단위로 나누는 작업) 시키는 방식의 차이로 나눠집니다. 학습 시간의 제한 때문에 character-unit의 방식을 선택했습니다.


## Module Installation

* 해당 모델을 실행하기 전 필요한 모듈을 설치해주세요
'''!pip install pandas
!pip install sentencepiece'''

* 아래 코드는 kospeech

## Inference One Audio with Pre-train Model

1. 하나의 오디오파일에 대한 음성인식 예측
 (코랩에서 사용시 경로 설정을 주의하세요 (device는 "cpu"로 설정하면 됩니다))

* command
`!python3 ./bin/inference.py --model_path $MODEL_PATH --audio_path $AUDIO_PATH --device $DEVICE`
	
* output
`음성인식 결과 문장`


## References

* kospeech : [https://github.com/sooftware/kospeech](https://github.com/sooftware/kospeech)
* letgodchan0 : [https://velog.io/tags/Kospeech](https://velog.io/tags/Kospeech)
