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

## 1. 트리와 그래프
- 트리는 재귀 호출과 실행 시간 분석에 관한 지식을 테스트 하기위해 좋은 자료

### 트리 
---
- 0개 이상의 다른 노드에 대한 레퍼런스(또는 포인터)가 들어있는 노드(데이터 원소)로 구성
- 한 노드를 참조하는 노드는 하나뿐
- 노드 := 구조체, 클래스로 표현된다

<code>
  public class Node{
  public Node[] children;
  }
  </code>
