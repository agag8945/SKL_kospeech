## SKL_KoreanSTT
# 한국어 STT 모델 개발 
해당 프로젝트는 한국어 음성인식 toolkit인 [kospeech](https://github.com/sooftware/kospeech)를 활용하여 개발하였습니다. 

# Introdution
* AIHUB에서 제공하는 [한국인 대화 음성의 데이터](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=130) 중 
broadcast_01 폴더와 life_09 폴더에서 각각 5만개씩의 데이터, 총 10만개의 데이터를 활용하여 음성인식 모델을 학습시켰습니다.
* 전처리 방식은 ~~~

# Module Installation

* 해당 모델을 실행하기 전 필요한 모듈을 설치해주세요
'''!pip install pandas
!pip install sentencepiece'''

* 아래 코드는 kospeech

# Inference One Audio with Pre-train Model

1. 하나의 오디오파일에 대한 음성인식 예측
 (코랩에서 사용시 경로 설정을 주의하세요 (device는 "cpu"로 설정하면 됩니다))

* command

`!python3 ./bin/inference.py --model_path $MODEL_PATH --audio_path $AUDIO_PATH --device $DEVICE`
	
* output

`음성인식 결과 문장`


# 
