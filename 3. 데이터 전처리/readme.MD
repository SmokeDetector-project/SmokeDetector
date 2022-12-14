## 주소지 통합
- 기준 인덱스: 주소 > 행정동 단위 
- 이슈: 각 파일별 주소지 입력 기준 상이 (도로명, 지번, 혼합, 위경도 등)
    - 주소 스페이스 처리: 주소 입력 양식 통일
    - 시/구/세부주소 분리
    - Kakao API 활용 -> 동일한 주소 양식으로 통일
    => 하나의 기준 (행정동)으로 통일

- 과태료:
  - 파일 내에 대전시 이외의 데이터 제거
  - kakao API에서 처리되지 않은 주소 데이터 처리
  - 최종 컬럼: 부과번호, 부과대상, 부과일자, 최종납기일자, 최초본세, 최종본세, 위도, 경도, 구, 행정동
  
- 금연구역: 
  - 데이터 분류: 구별 (유성구, 중구, 동구, 서구, 대덕구) 위경도 및 행정동명 추출
  - 결측치 (폐업, 유효하지 않은 주소 등), 불필요한 ( ) 공백, 특수문자 제거
  - 시, 구, 위경도, 행정동 추출
  - 최종 컬럼: 구, 구분, 시설명, 주소, 번지주소, 세부주소, kakao주소, 동, 위도, 경도, 행정동

- 목욕장:
  - 파일 내에 대전시 이외의 데이터 제거
  - 결측치 (폐업, 유효하지 않은 주소 등) 제거
  - 동 추출 (위경도는 이미 주어짐)
  - 최종 컬럼: 시, 구, 법정동, 사업장명, 소재지전체주소, 도로명전체주소, 좌표정보(x), 좌표정보(y)
  
- 병의원:
  - 파일 내에 대전시 이외의 데이터 제거
  - 최종 컬럼: 요양기관명, 종별코드명, 시군구코드명, 주소, 행정동, 위도(y), 경도(x) 
  
- 상권정보:
  - 이미 대전시만으로 정제된 데이터; 행정동 포함
  - 최종 컬럼: 상호-지점명, 상권업종대분류명, 상권업종중분류명, 상권업종소분류명, 시도명, 행정동명, 법정동명, 지번주소, 도로명주소, 경도, 위도
  
- 주차장 : 
   - 대전지역의 데이터만 추출, 소재지지번주소에서 `대전`이 포함된 데이터 추출
   - 지번주소 ()공백 제거
   - 최종 컬럼 : 시, 구, 법정동, KAKAO주소, 도로명주소, 위도, 경도
