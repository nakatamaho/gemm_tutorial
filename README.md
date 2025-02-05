# DGEMM 高速化のチュートリアル

本チュートリアルでは、C++ を用いて AMD64 (x86_64) アーキテクチャ上で動作する高速な倍精度行列‐行列積（DGEMM: General Matrix Multiply in double precision）の実装方法を解説します。行列の積は、数値計算や機械学習など、さまざまな分野で極めて重要な計算であり、その最適化は多くの応用で求められています。

一般的な DGEMM の演算は、以下の式で表されます:

$$
C \gets \alpha A B + \beta C
$$

ここで、

- **A, B, C** は行列  
- **α β** はスカラー

です。

本チュートリアルでは、CPU の L1、L2、L3 キャッシュの活用、AVX（SIMD）によるベクトル化、OpenMP を用いた並列化など、さまざまな最適化手法を駆使し、高速な GEMM の実装手順を段階的に解説していきます。

Web 上にはすでに優れたチュートリアルが数多く存在していますが、以下の3点に重点を置き解説してゆきます。

1. **一歩ずつ実行可能な実装手順の提示**  
   各段階でコードを実際に動作確認しながら実装できるため、初心者でも理解しやすい内容となっています。

2. **デバッグしやすい設計の採用**  
   行列をブロックに分割して処理する手法は、その正当性を視覚的に確認しにくいという課題がありますが、サンプル実装では行列ブロックを適宜プリントすることで、バグの原因究明や修正が容易になるよう工夫しています。

3. **一般の行列に対応した実装**  
   正方行列同士の積だけでなく、さまざまなサイズの行列に対応できるよう、ブロック化した後の端数部分の扱いも考慮しています。ただし転置は扱いません。

以下のリンクから、各章の詳細にアクセスできます。

- [01 DGEMMの紹介](#01-dgemmの紹介)
- [02 理論性能値の計算方法](02_flops.md#02-理論性能値の計算方法)
- [03 行列の取り扱い](03_matrix.md#03-行列の取り扱い)
- [04 もっとも簡単なDGEMMの実装](04_dgemm_naive.md#03-もっとも簡単な-dgemmの実装)
- [05 DGEMMの結果のプリントとチェック](05_print_and_benchmark.md#03-DGEMMの結果のプリントとチェック)
