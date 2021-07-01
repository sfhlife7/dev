건화 에러 해결

- frmMMA10.cs
    - L651에서 호출되는 M_CD = DBCMService.GetDB_M_CD(m_MNU_ID, ref iIndexNo); GetDB_M_CD함수에서 아래를 수정
        - CMService.cs L433: 검색조건에서 =를 LIKE로 수정
                     case "MMA10":
                        M_CD = CommonUtility.Right(GOGSGlobal.m_SHIP_NO, 4) + "-";
                        //SQLString = "SELECT M_CD FROM TMM_ORDER_REG WHERE M_CD='" + M_CD + "%' ORDER BY M_CD DESC";
                        SQLString = "SELECT M_CD FROM TMM_ORDER_REG WHERE M_CD LIKE '" + M_CD + "%' ORDER BY M_CD DESC";
    - 데이터 저장시 SHIP_NO, BLOCK_NO, ORDER_CD가 키이기 때문에 동일한 키로 입력된 데이터가 있으면 안됨을 주의할 것


출하관리(SDB10)
중조인계클릭시 출하대상이 없다고 나옴(현 상태가 생산임에도 대상이없다고 나오니 쿼리확인요망)
사급관리(MMA10)
저장 시 QR코드를 입력하라는 에러 발생
입고관리(LEA10)
클릭시 오류발생
계획관리(PPA10)
생산계획생성버튼 활성화안됨
KPI지표관리(PPB10)
목록 클릭 시 데이터 오류
검사관리(QMA10)
검사신청 버튼 활성화 안됨
불량관리(QMA20)
System.Data.SqlClient.SqlException: '열 이름 'M_CD'이(가) 유효하지 않습니다.
열 이름 'M_CD'이(가) 유효하지 않습니다.'
에러(74번줄, DBConn관련)

