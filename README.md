# 1. klay-es-plugin
klay(Korean Language AnalzYer) plugin for elasticsearch 

- 0.3 version : elasticsearch 6.5.0
  
* 다른 버전의 klay-es-plugin이 필요할 때 :
  - https://github.com/ks-shim/klay 에서 소스를 checkout하여 elasticsearch 버전을 변경한 다음 plugin을 재빌딩한다.
  - dwayne.shim@gmail.com으로 해당 버전의 klay-es-plugin을 요청한다.

# 2. Examples
  * 품사 정보는 http://kkma.snu.ac.kr/statistic?submenu=postag 를 참조해 주십시오.
## 2-1. 기본 사용
  - NNG, NNP, VV, VA, SL, SH, SN, NA 만 출럭합니다
```json
PUT test_index
{
  "settings": {
    "analysis": {
      "analyzer": {
        "klay_analyzer":{
          "type": "klay_analyzer"
        }
      }
    }
  }
}
```

## 2-2. 모든 형태소를 출력할 경우
```json
PUT test_index
{
  "settings": {
    "analysis": {
      "analyzer": {
        "klay_analyzer":{
          "type": "klay_analyzer",
          "usePosFilter":"false"
        }
      }
    }
  }
}
```

## 2-3. 특정 형태소만 출력할 경우
```json
PUT test_index
{
  "settings": {
    "analysis": {
      "analyzer": {
        "klay_analyzer":{
          "type": "klay_analyzer",
          "usePosFilter":"false",
          "allowedPoses" : ["NNG","VV"]
        }
      }
    }
  }
}
```
