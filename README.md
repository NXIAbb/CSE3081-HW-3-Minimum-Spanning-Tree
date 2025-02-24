Download Link :https://programming.engineering/product/cse3081-hw-3-minimum-spanning-tree/


# CSE3081-HW-3-Minimum-Spanning-Tree
CSE3081 HW 3: Minimum Spanning Tree
마감: 12월 26일 월요일 오후 8시 정각 (LATE 없음)

제출물 및 제출방법 등: 조교가 사이버 캠퍼스에 공지할 예정임.

목표: (1) 알고리즘 설계기법 중의하나인 greedy approach에 대한이해도를 높이도록 한다. (2) Prim과 Kruskal 의 Minimum Spanning Tree 알고리즘 각각을구현하여 본다. (3) 자신이구현한각방법의이론적인시간복잡 도와실제 수행 시간과의 관계를 분석하여 본다. (4) 대용량 그래프 처리를위한 효율적인자료구조 설계및 구현에 관하여연습하여 본다.

이번 숙제에서 사용하는 weigthed undirected graph G = (V, E)는다음과같은형식으로 ASCII 파일에 저장 되어있다.

334863 925872 65536

0 53525 25038

0 71631 17666

0 98005 16296

0 148223 1717

0 209319 5450

0 268298 29553

.

.

.

첫줄의 앞두 숫자는 각각 이 그래프의 vertex의 개수 n vertices와 edge의 개수 n edges를 나타낸다. 이줄의마지막숫자는 edge의 weight가가질수 있는가장큰 값 MAX WEIGHT를나타낸다(이때 edge의 weight는 1에서 MAX WEIGHT까지의 정수 값을 가질수 있음).

두번째줄부터는 n edges의 개수 만큼 각 edge에 대한 (from-verex ID, to-vertex ID, weight) 정보가 나열된다(이때 vertex ID는 0부터 n vertices-1까지의 값을 가지며, 이 그래프는 undirected graph임을 명심할 것). 이 그래프는 connected graph가 아닐 수도 있으며, 여러분은 그러한사항을 고려하 여프로그램을작성해야한다.

이번 숙제에서 제공하는 총 6개의 서로 다른 크기의 그래프들은 다음과 같은데, 이들은 모두 https://snap.stanford.edu/data/에서 제공하는 그래프들을 기반으로 생성하였다. 서강 사이버 캠퍼스에 공지하는링크에서 그래프들을다운로드 받아 이테이블의파일명으로변경한후 실험에 사용하라.

서강대학교 공과대학 컴퓨터공학과

(2/3)

file name

n

vertices

n

edges

HW3

email-Eu-core.txt

1,005

25,571

HW3

com-dblp.ungraph.txt

317,080

1,049,866

HW3

com-amazon.ungraph.txt

334,863

925,872

HW3

com-youtube.ungraph.txt

1,134,890

2,987,624

HW3

wiki-topcats.txt

1,791,489

28,511,807

HW3

com-lj.ungraph.txt

3,997,962

34,681,189

자신이작성한각 프로그램은 (i) Visual Studio의 solution directory에 존재하는이름이 commands.txt

인파일의첫 번째줄에서 입력 그래프파일이존재하는디렉터리정보를읽어 들여,

(commands.txt 파일 예)

C:\usr\local\Algorithm\HW 3\Graphs

HW3 com-dblp.ungraph.txt

HW3 com-dblp.ungraph MST result.txt

두번째줄의 파일에서 입력 그래프를읽어 들여 minimum spanning tree를 계산한 후, (iii) 위의 commands.txt 파일의 세 번째줄에 주어진 출력 파일에 그 결과를 ASCII 파일 형식으로 저장한다(주

의: 이파일은 commands.txt과동일한원래의 solution directory에 저장할것). 이 결과 파일의 형식을 다음과같은예를통하여 설명하면,

3

317024 2394950493

95433

67872

첫 줄에는 해당 그래프의 connected component의 개수가 주어지고, 다음 그 개수만큼의 줄 각각

에 (number of vertices in the component, total weight of minimum spanning tree) 정보를 기술해야 한다. 만약어떤 connected component가 한 개의 꼭지점으로 구성되어 있다 면(isolated vertex), 해당 줄에는 ‘1, 0’ 값이 저장되어야 하고, 전체 그래프가 connected되어 있다면 ‘n vertices, total weight of minimum spanning tree’ 정보가 저장되어야 한다.

Prim의 Minimum Spanning Tree 알고리즘을 구현할 때 시간복잡도가 O(|V |2) 방법이 아닌 수업 시간에 설명한 min heap에 기반을 둔 최악의 경우의 시간 복잡도가 O(|E| log |V |)인 방법을 구현하여야 한다.

또한 Kruskal의 Minimum Spanning Tree 알고리즘을 구현할 때에는 수업 시간에 설명한 disjoint sets과 min heap에 기반을 둔 최악의 경우의 시간 복잡도가 O(|E| log |V |)인 방법을 구현하여야 한다.

[주의] 이번 숙제에서는 실제 minimum spanning tree에 대한 정보를 출력할필요 없이 weight들의 총 합만 출력하면되나, 트리를 구축해가면서 어떻게하면효과적으로 tree 정보를 저장할 지 생각해볼것.

제출물 1: 자신이 구현한 소스 코드는이름이 HW 3 S20219999인 디렉터리 아래에 이름이 각각

Prim과 Kruskal인 디렉터리에 저장하여 zip으로 압축하여 보낼 것.

– 이때 그래프 데이터 파일과 .vs 등과같이 Visual Studio가 컴파일 및 수행 시 생성한 파일들은 반드시 삭제하고제출할 것.

– 채점을할 때, Visual Studio 2022 상에서 솔루션 구성은 Release로 그리고 솔루션 플랫폼은 x64

모드를사용할 예정이며, 만약 다른 구성을사용하여프로그램을작성한 것으로 인하여 컴파일 이안되거나 프로그램이수행이안될 경우 이는 본인의책임임을명심하라.

제출물 2: 보고서는이름이 HW3 S20219999.{hwp,docx,txt,pptx}인 파일을위에서 명시한 HW 3 S20219999 디렉터리 아래에 소스 코드와같이 저장하여 위의 zip 파일에 같이 제출하라. 즉 HW 3 S20219999 디렉터리 아래에는 두 개의 디렉터리와 하나의 (보고서) 파일이 저장된다.

– [CS3081(2반): 알고리즘 설계와분석] HW3 (2022년 12월 5일) –
