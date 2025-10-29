---
layout: page
title: Research
nav_order: 3
---

# Introduction to Our Research Topics (研究紹介)

最近の学位論文の題名一覧は[こちら](thesis_titles)を見てください. 

You can see recent thesis titles [here](thesis_titles).

# On-going topics

{% for topic in site.data.research_topics.ongoing %}
  <div class="research-item">
    * [{{ topic.title }}]({{ topic.url }})
    <span class="tags-container">
      {% for tag in topic.tags %}
        <span class="research-tag">#{{ tag }}</span>
      {% endfor %}
    </span>
  </div>
  {% endif %}
{% endfor %}
  
# Past topics

## High-Level, High-Performance General-Purpose Programming Frameworks

  * [MassiveThreads: Super Lightweight Thread Library](research/massivethreads)
  * [高性能なタスク並列スケジューラ](research/高性能なタスク並列スケジューラ)
  * [分散共有メモリ](research/分散共有メモリ)
  * [PerformanceAnalysisTools](research/performanceanalysistools)
  * [MPI+ULT](research/mpi_ult)
  * [Lightweight Threading Library and OpenMP Runtime System](research/lightweight_threading_library_and_openmp_runtime_system)
  * [GXP Parallel Shell/Scripting Tool](research/gxp)

## Very High-Level, High-Performance Domain-Specific Programming Frameworks

  * [大規模な文字列データ向けのアドホックな並列処理系](research/大規模な文字列データ向けのアドホックな並列処理系)
  * [CFG構文解析](research/cfg構文解析)
  * [ParaLite: Parallel Database](research/paralite)

## Deep Learning (深層学習)

  * [Analysis of Large Mini-Batch Training of Neural Networks](research/analysis_of_large_mini-batch_training_of_neural_networks)
  * Accelerating Neural Networks Having Dynamic Computation Graphs
  * [深層学習フレームワークの性能解析](research/深層学習フレームワークの性能解析)

## Storage and Operating System（ストレージとOS）

  * [次世代SSDによるVMMを用いたメモリ空間の拡張](research/次世代ssdによるvmmを用いたメモリ空間の拡張)
