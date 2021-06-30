건화 에러 해결

- frmMMA10.cs
    - L651에서 호출되는 M_CD = DBCMService.GetDB_M_CD(m_MNU_ID, ref iIndexNo); GetDB_M_CD함수에서 아래를 수정
        - CMService.cs L433: 검색조건에서 =를 LIKE로 수정
                     case "MMA10":
                        M_CD = CommonUtility.Right(GOGSGlobal.m_SHIP_NO, 4) + "-";
                        //SQLString = "SELECT M_CD FROM TMM_ORDER_REG WHERE M_CD='" + M_CD + "%' ORDER BY M_CD DESC";
                        SQLString = "SELECT M_CD FROM TMM_ORDER_REG WHERE M_CD LIKE '" + M_CD + "%' ORDER BY M_CD DESC";
    - 데이터 저장시 SHIP_NO, BLOCK_NO, ORDER_CD가 키이기 때문에 동일한 키로 입력된 데이터가 있으면 안됨을 주의할 것

입고관리(LEA10)
클릭시 오류발생
