# GPU_Programming

<br/>

전에는 일반적으로 연산의 효율을 위해서 3D 그래픽에서 (X,Y,Z,W) (R,G,B,a) 등의 형식으로 4개의 요소를 1개로 묶어 다뤘습니다.

<br/>

## SIMD(Single Instruction, Multiple Data)

### Intel SSE(Streaming SIMD Extensions), AVX(Advanced Vector Extensions)

<br/>

요즘은 데이터의 크기가 다양해서 위 방법은 경우에 따라 실효 성능이 저하됩니다.

<br/>

## SIMT(Single Instruction, Multiple Threading)

SIMD 실행에서는 각각의 명령으로 하나의 정점(X,Y,Z,W)을 하나로 묶어 처리하는데 4사이클이 소모되었습니다. <br/>
반면, SIMT 실행에서는 X,Y,Z,W 각 요소를 순서대로 처리 하므로 하나의 정점에 16사이클이 소모됩니다. <br/>
그러나 SIMT 방식은 이 때, 4개의 연산기가 각 다른 정점의 요소를 하나씩 처리하므로, <br/>
SIMD방식과 SIMT 모두 4개의 정점에 16사이클을 소모하는 것은 같습니다. <br/>
