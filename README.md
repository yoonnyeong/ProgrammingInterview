# ProgrammingInterview
# 『프로그래밍 면접 이렇게 준비한다.』 한빛미디어
<img src="https://github.com/yoonnyeong/ProgrammingInterview/blob/master/cover_image.jpg" width="360">

## 파일 구성

|폴더 이름   |설명                         |
|:--        |:--                          |
|ch04       |연결리스트                    |
|ch05       |트리와 그래프                 |
|ch06       |배열과 문자열                 |
|ch07       |재귀 호출                    |
|ch08       |정렬                         |
|ch09       |동시성                       |
|ch10       |객체지향 프로그래밍           |
|ch16       |지식기반문제                 |

##  트리와 그래프
- 트리는 재귀 호출과 실행 시간 분석에 관한 지식을 테스트 하기위해 좋은 자료

### 트리 
---
- 0개 이상의 다른 노드에 대한 레퍼런스(또는 포인터)가 들어있는 노드(데이터 원소)로 구성
- 한 노드를 참조하는 노드는 하나뿐
- 노드 := 구조체, 클래스로 표현된다
- 루트 : 최상위 노드; 다른 모든 노드로 가는 경로가 반드시 존재해야만 하는 유일한 노드 -> 모든 트리의 시작점은 루트
<pre>
<code>
  public class Node{
   public Node[] children; //노드가 참조하는 모든 노드를 저장할 배열
  }
  public class IntNode : Node {
    public int value;
  }
 </code></pre>
#### 1. 이진트리
- 보통 '트리'라 하면, 이진트리라고 일컫는 경우가 많다.
- 한 노드에 자식이 최대 두개까지 있을 수 있다.
- 그 두 자식은 각각 왼쪽 자식, 오른쪽 자식이라고 부른다.
<pre>
<code>
  
  class Node{
   private:
     Node left; //왼쪽 자식
     Node right; // 오른쪽 자식
     int value; // 노드의 값
   public:
     Node(Node left, Node right, int value){
        this.left = left;
        this.right = right;
        this.value = vaule;
    }
    
    Node getLeft(){return left;}
    Node getRight(){return right;}
    int getValue(){return value;}
  };
  </code>
  </pre>
#### 2. 이진 검색 트리 (Binary Search Tree)
- 트리에 데이터를 저장할 때, 흔히 쓰이는 자료구조
- BST에서는 노드의 왼쪽 자식의 값이 반드시 자신의 값 이하이고 , 오른쪽 자식의 값은 반드시 자신의 값 이상
         [나] <br>
        /    \ <br>
[나보다 작음][나보다 큼]  <br>
-**룩업 연산(look up)트리에 있는 특정노드의 위치를 알아내는 연산을 빠르고 간단하게 처리할 수 있음**
루트 노드에서 시작 <br>
현재 노드가 널이 아닌 동안 반복 <br>
현재 노드의 값이 찾고자 하는 값이면 <br>
 현재 노드를 리턴<br>
현재 노드의 값이 찾고자 하는 값보다 작으면<br>
 오른쪽 자식을 현재 노드로 설정 <br>
현재 노드의 값이 찾고자 하는 값보다 크면 <br>
 왼쪽 자식을 현재 노드로 설정 <br>
 반복문 끝 <br>
<pre><code>
Node findNode(Node root, int value){
  while(root!=null){ 
    int currval= root.getValue();
    if(currval == value) break;
    if(currval < value ){
      root = root.getRight();
    }
    else{
      root = root.getLeft();
    }
  
  }
  return root;
}

</code></pre>
