[두 장군 문제](obsidian://open?vault=LEO&file=%EC%A7%80%EC%8B%9D%2F%EC%9D%B4%EB%A1%A0%2F13.%20%EB%85%BC%EB%A6%AC%2F%EB%B6%84%EC%82%B0%2F%EB%91%90%20%EC%9E%A5%EA%B5%B0%20%EB%AC%B8%EC%A0%9C%20(%20%20Two%20Generals'%20Problem%20%20))의 연장선 문제


N명의 장군, 그리고 배신자가 있을수도 있다. 이때 모든 장군이 정확한 메세지를 수신할 수 있는가.

즉, N개의 노드와 노드가 오작동할 불확실성이 있는 환경에 메세지들이 올바르게 전파될 수 있는가에 관한 문제임.

결론은 2/3에 해당하는 장군이 있을경우 합의가 이루어 질 수 있음.

즉, 노드가 1/3까지 장애나도 **비잔틴 장애 허용** 합의 알고리즘을 사용한다면 시스템이 정상작동할 수 있음.

N개의 노드, f 개의 failure node 라고 할때 ( f노드라고 하겠음. )

F노드가 하는건 둘중 하나
- 메세지를 안보내거나
- 비정상 메세지를 보내거나

여기서 두 극단적인 경우를 생각해보면
- f노드 전부가 메세지를 안보내거나
- f노드 전부가 비정상 메세지를 보내거나.

N개의 노드가 quorum(합의)를 이루려면 과반수 이상의 투표를 얻어야하는데 

F노드 전부가 메세지를 안보내는 경우에도 시스템이 정상적으로 돌아가야만 하므로

전체 메세지 갯수인 N-f이
과반인 N/2 보다 커야한다.

즉, N - f > N/2 = N > 2f 여야한다.

하지만 갑자기 얘들이 심성이 뒤틀려서 f노드 전부가 비정상 메세지를 보내는 경우

N-f 노드 수로 쿼럼을 이루어 놨는데

정상 메세지 수인 N -f 
비정상 메세지 수인 f 를 뺀게
과반인 (N-f)/2 보다 커야함

즉,
(N-f) - f > (N - f )/ 2

N > 3f 라는 결론이 나옴.

즉, 극단의 극단 케이스까지 고려하면 N > 3f 일경우 비잔틴 장애 내성이 있다고 볼 수 있음.


참고
https://blog.seulgi.kim/2018/04/byzantine-fault-tolerance-n-3f-1.html
https://sjh9708.tistory.com/155

