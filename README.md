# gemm_tutorial

本チュートリアルでは、C++ を用いて AMD64 (x86_64) アーキテクチャ上で動作する高速な倍精度の行列‐行列積（DGEMM: General Matrix Multipy in double precision）の実装方法を解説します。 行列の積は、数値計算や機械学習などさまざまな分野で重要な計算であり、その最適化は多くの応用において求められています。

一般的な GEMM の演算は、以下の式で表されます:

$$
C \gets \alpha A B + \beta C
$$

ここで、

- **A, B, C** は行列
- **α, β** はスカラー

です。

本チュートリアルでは、CPU のL1, L2, L3キャッシュ活用、AVX(SIMD)化、OpenMPによる並列化などの最適化手法を駆使し、実際に高速な GEMM を実装する手順を段階的に説明していきます。

Web 上にはすでに優れたチュートリアルが数多く存在していますが、現代の CPU は複雑な構造と特殊なメモリアクセス特性を持つため、GEMM の実装は容易ではなく、途中で挫折してしまうケースも少なくありません。  特に、行列をブロックやパネルに分割して扱う手法は、紙上では理解しにくく、実装ミスがメモリ不正アクセスなどの深刻なバグにつながりやすいという問題があります。

そこで、本チュートリアルでは以下の2点に重点を置いて進めていきます。

1. **一歩ずつ実行可能な実装手順の提示**  
   各段階でコードを実際に動作確認しながら実装できるため、初心者でも理解しやすくなっています。

2. **デバッグしやすい設計の採用**  
   ブロック行列の処理や段階的な最適化を取り入れることで、バグの原因追及と修正を容易にしています。

このように、複雑な現代の CPU 環境においても扱いやすい GEMM の実装を目指し、わかりやすさと実用性を両立させた内容で進めていきます。  

以下のリンクから、各章の詳細にアクセスできます。

- [01 DGEMMの紹介](#01-dgemmの紹介)
- [02 理論性能値の計算方法](#02-理論性能値の計算方法)
- [03 もっとも簡単なDGEMMの実装](#03-もっとも簡単なdgemmの実装)


## 01 DGEMMの紹介

## 02-理論性能値の計算方法

## 03-もっとも簡単なdgemmの実装
