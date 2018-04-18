# Road Map

## User Responese Prediction

### Data

#### One-Hot Encoding

[[He et al., 2014] He, X., Pan, J., Jin, O., Xu, T., Liu, B., Xu, T., Shi, Y., Atallah, A., Herbrich, R., Bowers, S., et al. (2014). Practical lessons from predicting clicks on ads at facebook. In Proceedings of the Eighth International Workshop on Data Mining for Online Advertising, pages 1–ACM.](http://delivery.acm.org/10.1145/2650000/2648589/5-He.pdf?ip=218.197.152.122&id=2648589&acc=ACTIVE%20SERVICE&key=BF85BBA5741FDC6E%2E4977B3C8BBB4AEC7%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1524036768_bee6cd499f65a8f22fc73345569551f7)

### Models

#### Logistic regression with stochastic gradient descent

#### Online Learning

[美团点评技术团队：Online Learning算法理论与实践](https://zhuanlan.zhihu.com/p/22127646).

- FTRL: Follow-The-Regularised-Leader proximal (FTRL-proximal)

  [McMahan et al., 2013] McMahan, H. B., Holt, G., Sculley, D., Young, M., Ebner, D., Grady, J., Nie, L., Phillips, T., Davydov, E., Golovin, D., et al. (2013). Ad click prediction: a view from the trenches. In Proceedings of the 19th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining, pages 1222–1230. ACM.

- BPR: Bayesian Probit Regression

  [Graepel et al., 2010] Graepel, T., Candela, J. Q., Borchert, T., and Herbrich, R. (2010). Web-scale bayesian click-through rate prediction for sponsored search advertising in microsoft’s bing search engine. In Proceedings of the 27th International Conference on Machine Learning, pages 13–20.

#### Factorisation Machines (FM)

计算广告与机器学习：[第09章：深入浅出ML之Factorization家族](http://www.52caml.com/head_first_ml/ml-chapter9-factorization-family/).

#### Decision Tree

#### Ensemble Learning

周志华《机器学习》：第8章 集成学习

- Bagging
- GBDT
  - 李航《统计学习方法》：5.5 CART算法
  - Blog：[GBDT：梯度提升决策树](https://www.jianshu.com/p/005a4e6ac775).
  - Blog:  [GBDT（MART） 迭代决策树入门教程 | 简介](https://blog.csdn.net/suranxu007/article/details/49910323).
- Hybrid Models
  - [He et al., 2014] He, X., Pan, J., Jin, O., Xu, T., Liu, B., Xu, T., Shi, Y., Atallah, A., Herbrich, R., Bowers, S., et al. (2014). Practical lessons from predicting clicks on ads at facebook. In Proceedings of the Eighth International Workshop on Data Mining for Online Advertising, pages 1–ACM.
  - [[Juan et al., 2016] Juan, Y., Zhuang, Y., Chin, W.-S., and Lin, C.-J. (2016). Field-aware factorization machines for CTR prediction. In Proceedings of the 9th ACM Conference on Recommender Systems.](http://delivery.acm.org/10.1145/2960000/2959134/p43-juan.pdf?ip=218.197.152.122&id=2959134&acc=ACTIVE%20SERVICE&key=BF85BBA5741FDC6E%2E4977B3C8BBB4AEC7%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1524036545_14efbcf3087694a32590bae1effaffce)

#### User lookalike modelling

[[Zhang et al., 2016a] Zhang, W., Chen, L., and Wang, J. (2016a). Implicit look-alike modelling in display ads: Transfer collaborative filtering to ctrestimation. In European Conference on Information Retrieval, pages 589–Springer.](http://wnzhang.net/share/rtb-papers/cf-ctr.pdf)

#### Transfer Learning

[[Zhang et al., 2016a] Zhang, W., Chen, L., and Wang, J. (2016a). Implicit look-alike modelling in display ads: Transfer collaborative filtering to ctrestimation. In European Conference on Information Retrieval, pages 589–Springer.](http://wnzhang.net/share/rtb-papers/cf-ctr.pdf)

#### Deep Learning

- Factorisation Machine supported Neural Network (FNN) and Sampling-based Neural Network (SNN)

  [[Zhang et al., 2016b] Zhang, W., Du, T., and Wang, J. (2016b). Deep learning over multi-field categorical data. In European Conference on Information Retrieval, pages 45–57. Springer.](http://wnzhang.net/share/rtb-papers/deep-ctr.pdf)

- [[Qu et al., 2016] Qu, Y., Cai, H., Ren, K., Zhang, W., Yu, Y., Wen, Y., and Wang, J. (2016). Product-based neural networks for user response prediction. In IEEE 16th International Conference on Data Mining.](https://arxiv.org/pdf/1611.00144.pdf)

- [[Zhang et al., 2014c] Zhang, Y., Dai, H., Xu, C., Feng, J., Wang, T., Bian, J., Wang, B., and Liu, T.-Y. (2014c). Sequential click prediction for sponsored search with recurrent neural networks. In Twenty-Eighth AAAI Conference on Artificial Intelligence.](http://www.aaai.org/ocs/index.php/AAAI/AAAI14/paper/download/8529/8581)

### Model Comparison
From [Display Advertising with Real-Time Bidding (RTB) and Behavioural Targeting](https://arxiv.org/abs/1610.03013) by Jun Wang, Weinan Zhang and Shuai Yuan. ArXiv 2016.
> As discussed in this chapter, there are various user response prediction mod-els. From the modeling perspective, these models can be generally cate-gorised as linear and non-linear models.
>
> Linear models, including logistic regression [Lee et al., 2012, McMahanet al., 2013] and Bayesian probit regression (with diagonal covariance matrix)[Graepel et al., 2010], directly build the model based on the feature independence assumption. For linear models, the feature interaction patterns are generally captured by building large-scale feature space with combining multi-field features, which could consume much human effort. **However, thanks to its high efficiency and high parallelization capability, linear models are able to be fed in much more training data instances (and higher dimensional features) during the same training period, which makes them still highly comparable with the non-linear models in many industrial environments**.
>
> Non-linear models, including factorisation machine [Rendle, 2010, Juanet al., 2016], tree models [He et al., 2014] and recently emerged (deep) neural networks models [Zhang et al., 2016b, Qu et al., 2016], provide model capacity of **automatically learning feature interaction** patterns without the need of designing combining features. These non-linear models generally need much more computation resources than the linear ones, and some of themmay require multiple stages of model training, as demostrated in [He et al.,2014]. With the fast development high performance computing (HPC) andthe explosion of data volume, non-linear models are more and more appliedin commercial platforms for practical user response prediction.

## News

知乎收藏夹：[RTB](https://www.zhihu.com/collection/234402874).

知乎收藏夹：[Research](https://www.zhihu.com/collection/146175275).

- [【阿里算法天才盖坤】解读阿里深度学习实践，CTR 预估、MLR 模型、兴趣分布网络等](https://zhuanlan.zhihu.com/p/35599271).
- [周志华最新演讲：深度学习为什么深？有多好的人才，才可能有多好的人工智能](https://zhuanlan.zhihu.com/p/35730947).