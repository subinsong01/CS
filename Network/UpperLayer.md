<img width="675" alt="스크린샷 2024-06-08 오후 11 43 05" src="https://github.com/subinsong01/TIL/assets/134045937/56e544a0-a419-451f-92c5-ed7b78589fae">

 1. Network Layer(경로 설정)
    1. 소스로부터 패킷을 목적지까지 전송한다
        - 여러 네트워크들의 연결
        - 혼잡 제어
        - internetworking 환경에 공통 주소를 제공한다
            
            [ Internetworking  : router, gateway, protocol ]
            
         <img width="622" alt="스크린샷 2024-06-08 오후 11 45 03" src="https://github.com/subinsong01/TIL/assets/134045937/f3be6153-1437-4dae-b033-b566146ce3af">

           
    2. 목적지에 도달하기 위해 중간 노드에서 많은 홉을 필요로 한다.
       
    - 홉(hop)은 데이터가 한 노드에서 다음 노드로 이동할 때마다 발생하는 단계를 의미합니다. 많은 홉을 거친다는 것은 데이터 패킷이 여러 중간 지점을 통과해야 함을 나타낸다.
      
    - subnet을 통해서 패킷을 라우팅한다.
    
    3. 다른 네트워크들 사이에서 communication을 제공해준다.
    
    - Topology, Protocol, Transmission speed, Maximum packet size.
      
    - Addressing difference of the communication subnet
    
    4. 하위 네트워크에(underlying network)서 전송 계층(transport layer)로 투명한 서비스를 제공한다
    
    - 서비스는 subnet tecnology에서 독립되어야 한다
    - Transport layer는 존재하는 subnet의 숫자와, 타입, 그리고 topology로부터 보호받아야 한다.
        
        [ 문장은 전송 계층이 네트워크 하위 계층의 복잡성으로부터 독립적으로 작동해야 한다는 의미를 담고 있다. 즉, 전송 계층은 네트워크의 다양한 서브넷의 수나 유형, 구조(토폴로지)에 영향을 받지 않고 안정적으로 데이터를 전송할 수 있어야 한다는 것이다. 이를 통해 전송 계층은 보다 단순하고 일관된 방식으로 데이터 전송을 관리할 수 있다]

  2. Transport Layer(전송)
     
      1.  connection management
    
      2. source로부터 목적지까지 신뢰성 있는 packet을 전송한다. *(신뢰도)*
  
              1. Congestion control (혼잡 제어) : 중계 노드의 버퍼관리를 위한 전송 속도 조절)
              
              2. Error Control : 손실된 패킷, 중복된 패킷, 파손된 패킷
              
              3. Flow Control : 버퍼 관리

  3. Session Layer(세션) 
     
      1. Transport layer에서 제공하는 기능을 최대한 이용하여 개발,  응용 프로그램에서 항상 필요로 하는 공통적인 기능을 제공
         
      2. Session management  : 회의기간관리
             
              1. 세션 설정: 통신을 시작하기 위해 송신자와 수신자 간의 세션을 설정합니다.
              2. 세션 유지: 세션이 활성화되어 있는 동안 통신을 관리하고 유지합니다.
              3. 세션 종료: 통신이 완료되면 세션을 정상적으로 종료합니다.
           
      3. Dialog management(대화 제어) : 양방향 통신이 가능하도록 대화(또는 대화의 단방향 흐름)를 관리합니다. 반이중(half-duplex) 또는 전이중(full-duplex) 통신 방식을 지원한다.
         
      4. Synchronization(**동기화)** : 데이터 전송 중에 체크포인트나 동기화 점을 설정하여 전송이 중단되더라도 중단된 지점부터 다시 시작할 수 있게 합니다.
     
      6. Activity management : 회의 기간 중의 여러 활동의 조정 및 관리
