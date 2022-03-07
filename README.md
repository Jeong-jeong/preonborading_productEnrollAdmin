# 목표는 취업이조

## 🚀 정보

- [배포주소 바로가기](https://goalisemployment.s3.ap-northeast-2.amazonaws.com/index.html)
- [노션 바로가기](https://sleepy-oxygen-343.notion.site/41970b5fee2d45aebd7b01de061039eb)
- [원본 레포지토리 바로가기](https://github.com/wanted-team2/1week_productEnrollAdmin)

## 🧐 프로젝트 빌드 및 실행 방법

1. 상단 `Code` 버튼을 눌러 레포지토리를 클론 받습니다.

```
$ git clone https://github.com/wanted-team2/1week_productEnrollAdmin.git
```

2. 패키지를 설치합니다.

```
$ yarn install
```

3. 서버를 실행합니다.

```
$ yarn start
```

## 😎 팀원

| [김지영(팀장)](https://github.com/Jeong-jeong) | 고병표 | 유제호 | 홍수연 |
| --- | --- | --- | --- |
| <img src="https://user-images.githubusercontent.com/68528752/153546074-abd9a7df-771c-4f14-8a2f-a77246210b1c.jpeg" width="400px"/> | <img src="https://user-images.githubusercontent.com/68528752/153546140-b58f43fe-4730-46ca-bfda-0b048f36d24f.JPG" width="400px"/> | <img src="https://user-images.githubusercontent.com/68528752/153545718-c688e091-53a3-4e30-97fd-a2f00ab97aa8.JPG" width="400px"> | <img src="https://user-images.githubusercontent.com/68528752/153545721-ecc413f4-9d1b-45e0-9909-423c27128b1c.jpeg" width="400px"> |
| [🚀 회고](https://velog.io/@jeongs/3주차-회고) |  |  |  |

## 🌈 담당

### 공통 기능

- PropTypes, defaultProps로 props 타입 체크

### 담당한 기능

- 프로젝트 기초 세팅, prettier, eslint, style theme, craco 절대 경로 설정
- form 태그의 시멘틱 속성을 활용해 필수값 체크 및 코드량 감소
- onChange 발생 시 디바운스를 활용해 `실시간 자동 저장 기능` 구현
- `상품 옵션 테이블(OptionTable)` 구현

  - 옵션 세트 추가, 삭제
  - 옵션 이미지 추가
  - 옵션 세트 내 옵션 추가, 삭제
  - 옵션 세트 내 옵션 내 추가, 삭제
  - 옵션 세트 내 옵션을 모두 삭제하면 옵션 세트 또한 삭제 ![기본 옵션 세트 데모](https://images.velog.io/images/jeongs/post/f0badd5f-87f4-48d7-928e-1e1a4afe4e1d/%EC%83%81%ED%92%88%EC%98%B5%EC%85%98%EB%8D%B0%EB%AA%A81.gif)
  - 할인율 처리
    - 할인율 소수점 버림 처리
    - 정상가, 판매가 같을 경우 `할인율 없음` 표시
  - 재고 처리
    - 옵션 세트 내 모든 옵션에 대한 총 재고 수량 저장 ![재고 데모](https://images.velog.io/images/jeongs/post/eb3afd7a-d577-4e21-b1ee-0075e2805358/%ED%95%A0%EC%9D%B8%EC%9C%A8_%EC%9E%AC%EA%B3%A0.gif)
  - 비과세, 과세 처리

    - 과세 옵션 선택 시 해당 옵션의 저장된 판매가의 부과세(VAT) 10%로 저장 ![비과세처리 데모](https://images.velog.io/images/jeongs/post/755109c2-7ac7-4160-89ed-a1933968e1eb/%EA%B3%BC%EC%84%B8.gif)

  - 상품 옵션 테이블 데이터 구조

  ```js
  {
    index: 0, // 각 옵션세트 인덱스
    imageInfo: {},
    optionInfo: [ // 옵션 세트 내 옵션 정보
    {
      index: 0,
      optionName: '',
      normalPrice: 0, // 정상가
      price: 0, // 할인가
      discount: 0,
      stock: 0,
      isVAT: true,
      VAT: 0, // 부과세
      },
    ],
    totalStock: 0, // 옵션 세트 내 모든 옵션의 stock 총합
    additoryOptions: [ // 옵션 세트 내 옵션 내 추가
    {
      index: 0,
      addOptionName: '',
      addOptionNormalPrice: 0,
      },
    ],
  }
  ```

- `상품 정보고시 테이블(ItemInformationTable)` context 분리, 및 리팩토링

<br>
<br>

## 📈 디렉토리 구조

```
.
├── README.md
├── babel.config.js
├── craco.config.js
├── jest.config.js
├── package.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── robots.txt
│   └── tags.json
├── src
│   ├── App.jsx
│   ├── assets
│   ├── components
│   ├── contexts
│   ├── hooks
│   ├── pages
│   ├── setupTests.js
│   ├── style
│   └── utils
│   ├── index.jsx
└── yarn.lock
```
