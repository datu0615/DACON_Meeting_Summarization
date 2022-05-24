# DACON_Meeting_Summarization
![20220524_125338](https://user-images.githubusercontent.com/84311270/169947589-5ee861f5-562e-462e-89a0-3020801b355f.png)
문서화된 회의 녹취록에서 핵심 내용을 요약하는 생성요약 AI모델 개발

## Dataset
1. train.json : 학습용 데이터셋  
 ├ id : 회의록 id  
 ├ region : 회의 지역  
 ├ num_agenda : 안건 수  
 │ ├ AGENDA_1 : 안건1  
 │ ├ AGENDA_2 : 안건2  
 │ ├ AGENDA_3 : 안건3  
 │ └ ...  
 └ label : 안건별 요약문  
   ├ AGENDA_1 : 안건1의 요약문  
   │ ├ evidence : 요약 근거  
   │ └ summary : 요약문(정답)  
   ├ AGENDA_2 : 안건2의 요약문  
   │ ├ evidence : 요약 근거  
   │ └ summary : 요약문(정답)  
   ├ AGENDA_3 : 안건3의 요약문  
   │ ├ evidence : 요약 근거  
   │ └ summary : 요약문(정답)  
   └ ...

2. test.json : 평가용 데이터셋  
 ├ id : 회의록 id  
 ├ region : 회의 지역  
 ├ num_agenda : 안건 수  
 └ context : 회의내용  
   ├ AGENDA_1 : 안건1  
   ├ AGENDA_2 : 안건2  
   ├ AGENDA_3 : 안건3  
   └ ...  

3. sample_submission.csv : 제출용 양식  
 uid : test.json의 안건별 고유 id ('id2000-AGENDA_1 : id2000회의의 안건1)  
 summary : 안건의 요약문  
 
## Model
불용어나 필요없는 기호에 대한 전처리 진행 후 KoBART 모델을 사용하여 학습을 진행.

## Results
최종 55등으로 마무리.
![20220524_125459](https://user-images.githubusercontent.com/84311270/169947600-74a62d94-3b95-4a0c-b743-8e8d8145737f.png)
