# LG_Aimers 4기 

교육기간 : 2024.01.02 ~ 2024.02.26
Phase I 온라인 AI 교육 : AI기술 전반에 대한 이해, 해커톤 문제를 풀기 위해 필요한 도메인 지식 습득
Phase II 온라인 해커톤 : LG 계열사가 보유한 산업의 현장 Data를 기반으로 AI를 활용하여 문제를 해결

### 영업 성공 여부 분류 경진대회

## 해커톤 배경
기업은 MQL(Marketing Qualified Leads)을 생성하고 관리함으로써 잠재 고객을 찾고 모니터링하여 이를 영업 기회로 전환하는 과정에 많은 시간과 자원을 투자합니다. 최근 기계학습 분야가 크게 발전하게 된 만큼 연구도 활발해져서 기존의 전통적인 모델보다 더 높은 성능을 내는 모델도 다수 등장하고 있습니다.
따라서 영업 기회 전환 고객을 선별하기 위한 AI모델을 개발하는 것은 미래의 영업 기회를 예측할 수 있고 데이터에 기반한 의사 결정을 강화할 수 있습니다. 더불어, 해커톤은 기업들이 AI 기술을 활용하여 경쟁력을 강화하고 혁신적인 솔루션을 개발하는 기회의 창을 제공하며, 이를 통해 새로운 비즈니스 기회를 탐색하고 기업의 성장을 촉진할 수 있습니다.

이러한 배경 아래 이번 해커톤에서는 MQL 데이터를 활용하여 영업 기회 전환을 예측하는 AI 모델을 구현하고 그 성능을 비교하는것에 초점을 맞추고자 합니다.

이를 통해, 이론 기반의 지식 습득을 넘어서 AI이론을 실제 활용할 수 있는 기회를 제공하며 현장의 실제 Data를 기반으로 AI를 활용하여 문제를 해결하는 과정을 통해 실무 경험을 체험할 수 있을 것입니다.

## 영업 성공 여부 분류 경진대회 개요

최근 기계학습 분야가 크게 발전하게 된 만큼 연구도 활발해져서 기존의 전통적인 모델보다 더 높은 성능을 내는 모델도 다수 등장하고 있습니다. 더불어서 영업 과정에서 전환 가능성이 높은 고객에게 영업 자원을 집중하기 위해 고객의 전환 여부를 예측하기 위해 기계학습을 도입하고 있습니다.

따라서 이번 경진대회에서는 고객의 다양한 정보를 보고 해당 고객이 전환 고객인지 아닌지를 판단하는 모델을 구현하고 그 성능을 비교하고자 합니다.

## Dataset Info.

### feature 정리

1) bant_submit : MQL 구성 요소들 중 [1]Budget(예산), [2]Title(고객의 직책/직급), [3]Needs(요구사항),  [4]Timeline(희망 납기일)  :  4 가지 항목에 대해서 작성된 값의 비율
2) customer_country : 고객의 국적
3) business_unit MQL : 요청 상품에 대응되는 사업부
4) com_reg_ver_win_rate  :  Vertical Level 1, business unit, region 을 기준으로 oppty 비율을 계산
5) customer_idx  :  고객의 회사명
6) customer_type  :  고객 유형
7) enterprise : Global 기업인지, Small/Medium 규모의 기업인지
8) historical_existing_cnt  :  이전에 Converted(영업 전환) 되었던 횟수
9) id_strategic_ver :  (도메인 지식) 특정 사업부(Business Unit), 특정 사업 영역(Vertical Level1)에 대해 가중치를 부여
10) it_strategic_ver : (도메인 지식) 특정 사업부(Business Unit), 특정 사업 영역(Vertical Level1)에 대해 가중치를 부여
11) idit_strategic_ver  :  Id_strategic_ver 이나 it_strategic_ver 값 중 하나라도 1 의 값을 가지면 1 값으로 표현
12) customer_job  :  고객의 직업군
13) lead_desc_length  :  고객이 작성한 Lead Descriptoin 텍스트 총 길이
14) inquiry_type  :   고객의 문의 유형
15) product_category  :  요청 제품 카테고리
16) product_subcategory  :  요청 제품 하위 카테고리
17) product_modelname  :  요청 제품 모델명
18) customer_country.1  :  담당 자사 법인명 기반의 지역 정보(대륙)
19) customer_position  :  고객의 회사 직책
20) response_corporate  :  담당 자사 법인명
21) expected_timeline  :  고객의 요청한 처리 일정
22) ver_cus :  특정 Vertical Level 1(사업영역) 이면서 Customer_type(고객 유형)이 소비자(End-user)인 경우에 대한 가중치
23) ver_pro  :  특정 Vertical Level 1(사업영역) 이면서 특정 Product Category(제품 유형)인 경우에 대한 가중치
24) ver_win_rate_x  : 전체 Lead 중에서 Vertical 을 기준으로 Vertical 수 비율과 Vertical 별 Lead 수 대비 영업 전환 성공 비율 값을 곱한 값
25) ver_win_ratio_per_bu  :  특정 Vertical Level1 의 Business Unit 별 샘플 수 대비 영업 전환된 샘플 수의 비율을 계산
26) business_area  :  고객의 사업 영역
27) business_subarea  :  고객의 세부 사업 영역
28) lead_owner  :  영업 담당자 이름
29) is_converted  :  영업 성공 여부. True 일 시 성공.

![피처](https://github.com/mJekal/ss/assets/132838012/9f6bb2c5-f5ff-40bc-bccf-451d2f3d86fe)

### 모델 학습용 데이터셋 (train.csv)

데이터 셋은 고객의 다양한 정보를 기록한 데이터와 해당 고객의 영업이 성공으로 전환되었는지 알려주는 라벨 데이터로 이루어져 있습니다.

### 제출용 테스트 데이터셋 (submission.csv )
제출용 데이터는 공정한 평가를 위해 일부 데이터를 추출한 것으로 학습용 데이터와 True와 False의 분포가 다릅니다.

### 결과 지표 (classification 지표)
F1 Score

​




