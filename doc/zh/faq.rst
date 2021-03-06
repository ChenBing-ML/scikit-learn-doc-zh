.. _faq:

===========================
常见问题
===========================

在这里，我们试着给出一些经常出现在邮件列表上的问题的答案。

项目名称是什么(很多人弄错)?
--------------------------------------------------------
scikit-learn, 不是scikik、SciKit、sci-kit learn，也不是我们曾使用的scikits.learn和scikits-learn。

如何称呼scikit-learn?
------------------------------------------
sy-kit learn。sci代表着科学!

选择 scikit的理由 ?
----------------------------
scikit拥有很多围绕Scipy构建的科学工具箱。你可以在 `<https://scikits.appspot.com/scikits>` 查找工具列表。 `scikit-image <http://scikit-image.org/>` 和 scikit-learn_一样受欢迎 。


如何才能为 scikit-learn 贡献自己的力量?
---------------------------------------------
在添加一个通常是重要冗长的新算法前, 推荐你观看
:ref:`known issues <new_contributors>` 。
关于 scikit-learn 贡献，请不要直接和 scikit-learn 的贡献者联系。

获得scikit-learn用法的最佳方法？
--------------------------------------------------------------
**对于一般的机器学习问题**, 请使用
`交叉验证 <http://stats.stackexchange.com>`_ 和 ``[machine-learning]`` 。

**对于scikit-learn使用的问题**, 请点击 `Stack Overflow <http://stackoverflow.com/questions/tagged/scikit-learn>`_ 中带有 ``[scikit-learn]`` 和 ``[python]`` 标签的部分。 你也可以使用 `联系列表 <https://mail.python.org/mailman/listinfo/scikit-learn>`_ .

请确保包您的代码段较小(最好少于10行)，并且可以突出显示玩具数据集上的问题 (例如从 ``sklearn.datasets`` 或者是用固定随机数种子 ``numpy.random`` 函数生成). 请删除任何不需要重现您的问题的代码行。该问题因该可以在安装了scikit-learn的python命令行中简单地通过复制粘贴您的代码重现. 并且不要忘了import语句.

编写能够重现的代码的更多指南可以在以下网址找到:
http://stackoverflow.com/help/mcve

你的代码依旧引起了你即使Google过也不明白的异常，请确保你在运行复制的脚本时包含完整的回溯。

关于错误报告或者功能请求，请参阅 `issue tracker on Github <https://github.com/scikit-learn/scikit-learn/issues>`_ 。

你还可以在 `scikit-learn Gitter channel <https://gitter.im/scikit-learn/scikit-learn>`_ 找到一些用户与开发人员。

**请不要直接给任何作者发邮件请求帮助，报告bug或其他与scikit-learn相关的问题。**

如何创建一个 bunch 对象?
------------------------------------------------

不要创建 bunch 对象，他们不是 scikit-learn API 的一部分. Bunch 对象只是打包一些 numpy 数组的方式.  numpy 数组只是为scikit-learn 用户的模型提供数据的工具。

例如，训练一个分类器, 你只需要一个2D的输入变量数组 ``X`` 和一个1D目标变量数组 ``y``  。 ``X`` 数组将特征作为列，样本保存为行。 ``y`` 数组包含用于对每个样本的类成员资格编码的整型数值 ``X``.

如何将我自己的数据集加载到 scikit-learn 可用的格式?
--------------------------------------------------------------------

一般来说,scikit-learn 可以在诸如 numpy 数组或者 scipy 稀疏矩阵这样的数字数据上运行。其他格式的如 pandas Dataframe 的数组也是可以的。

有关将数据文件加载到可用数据结构中的更多信息，参阅 :ref:`加载外部数据集 <external_datasets>` 。

新算法的纳入标准是什么 ?
----------------------------------------------------

我们仅考虑添加已经完善的算法。通常的标准是发布3年以上，被引用超过 200 次，而且被广泛使用。对广泛使用的方法提供了明确改进的技术（如增强型数据结构或更有效的近似技术）也将被考虑纳入。

在满足上述标准的算法或技术中,只有这些能够 ``适合`` 现在 scikit-learn API 的, ``预测/转换`` 接口通常具有 numpy 阵列或稀疏矩阵的输入/输出。

贡献者应该支持通过研究论文或其他类似软件包中的实现来增加提出算法技术的重要性，通过常见的用例或应用程序证明其有用性，并通过基准和/或图证实性能改进（如果有的话）。预计所提出的算法应该在某些领域优于已经在 scikit-learn 中实现的方法.

还要注意，您的实现不需要在 scikit-learn 中与 scikit-learn 工具一起使用。您可以用 scikit-learn 兼容的方式实现您最喜欢的算法，将其上传到 github 便于我们获知。我们将在 :ref:`related_projects` 列出。

.. _selectiveness:

为什么你对 scikit-learn 中的算法如此讲究?
------------------------------------------------------------------------
代码是需要维护的, 我们需要平衡我们的团队规模和代码量(并且：复杂性与特征的数量非线性相关). 该软件包依赖于核心开发人员利用他们的空闲时间修复错误，维护代码和审查贡献。
添加的任何算法都需要开发人员的密切，但此时原作者可能早已失去兴趣。
也可以在 `该链接 <https://sourceforge.net/p/scikit-learn/mailman/scikit-learn-general/thread/CAAkaFLWcBG+gtsFQzpTLfZoCsHMDv9UG5WaqT0LwUApte0TVzg@mail.gmail.com/#msg33104380>`_ 查看。

为什么从 scikit-learn 中删除 HMMS ?
----------------------------------------------------
:ref:`adding_graphical_models` 。 

.. _adding_graphical_models:

未来 scikit-learn 中会添加图形模型或序列预测吗?
---------------------------------------------------------------------

目前可能性不大 scikit-learn 尝试为机器学习中的基本任务提供统一的 API，使用管道和元算法（如网格搜索）将所有内容都集中在一起。 结构化学习所需的概念，API ，算法和专业知识与 scikit learn 所提供的不同。如果我们开始进行随意的结构化学习，那么我们需要重新设计整个软件包，这个项目可能在自身的负担下崩溃。

这里有两个类似于 scikit-learn 的做结构化预测的 API:

* `pystruct <http://pystruct.github.io/>`_ 处理一般结构化学习
(专注于具有近似推理的任意图形结构上的 SSVMs ; 将样本的概念定义为图形结构的一个实例)

* `seqlearn <http://larsmans.github.io/seqlearn/>`_ 仅处理序列（专注于精确推断;主要是为了完整性附带了 HMMs ;将特征向量作为样本，并对特征向量之间的依赖使用偏移编码）

你会添加 GPU 支持吗?
----------------------------------

目前不会，主要在于 GPU 支持将引入许多软件依赖关系并引入平台特定的问题。scikit-learn 旨在轻松安装在各种平台上。除了神经网络，GPU 在当今的机器学习中不起重要作用，通常我们可以通过仔细选择算法来获得更大的速度增益。

你支持 PyPy 吗?
-----------------------------

如果您不知道 `PyPy <http://pypy.org/>`_ 它是个新的，快速，及时的编译 Python 实现，但是我们不支持。若 PyPy 中的 `NumPy support <http://buildbot.pypy.org/numpy-status/latest.html>`_ 已经完善或接近完善，并且 SciPy 也被移植时，我才会考虑移植。 scikit-learn 使用了太多的 NumPy 所以不能完成部分实现。

如何处理字符串数据（或树，图...）？
-----------------------------------------------------

scikit-learn 估计器假设您将为他们提供实值特征向量。这个假设在几乎所有的库都是硬编码的。但是，您可以通过多种方式将非数字输入馈送到估计器。

如果您有文本文档，可以使用术语频率特征; 参阅内置 *文本向量化器* 的
:ref:`text_feature_extraction` 。
对于从任何类型的数据更一般的特征提取，见
:ref:`dict_feature_extraction` 和 :ref:`feature_hashing` 。

另一个常见的情况是当您对这些数据有非数字数据和自定义距离（或相似度）指标时。示例包括具有编辑距离的字符串（也称为 Levenshtein 距离;例如 DNA 或 RNA 序列）。这些可以编码为数字，但这样做通常很麻烦也容易出错。使用任意数据的距离度量可以通过以下两种方式完成。

首先，许多估计器采用预计算的距离/相似矩阵，因此如果数据集不太大，可以计算所有输入对的距离。如果数据集很大，您可以使用仅具有一个“特征”的特征向量，该特征是单独数据结构的索引，并提供在该数据结构中查找实际数据的自定义度量函数。
例如，使用 DBSCAN 与 Levenshtein 距离::

    >>> from leven import levenshtein       # doctest: +SKIP
    >>> import numpy as np
    >>> from sklearn.cluster import dbscan
    >>> data = ["ACCTCCTAGAAG", "ACCTACTAGAAGTT", "GAATATTAGGCCGA"]
    >>> def lev_metric(x, y):
    ...     i, j = int(x[0]), int(y[0])     # extract indices
    ...     return levenshtein(data[i], data[j])
    ...
    >>> X = np.arange(len(data)).reshape(-1, 1)
    >>> X
    array([[0],
           [1],
           [2]])
    >>> dbscan(X, metric=lev_metric, eps=5, min_samples=2)  # doctest: +SKIP
    ([0, 1], array([ 0,  0, -1]))

(这里使用了第三方编辑距离包 ``leven``)

类似的技巧也可以在树形内核、图形内核等使用。

为什么我有时会在 OSX 或 Linux 下遇到 n_jobs > 1 崩溃/冻结?
----------------------------------------------------------------------------------------

一些例如 ``GridSearchCV`` 和 ``cross_val_score`` 的scikit-learn工具，它们可以依靠 Python 的内置 `multiprocessing` 模块，通过 ``n_jobs > 1`` 作为参数，将执行并行化到多个 Python 进程。

问题是 Python 由于性能原因 ``multiprocessing`` 会执行 ``fork`` 系统调用，而不是 ``exec`` 系统调用。许多库如 OSX 下的（某些版本的）Accelerate / vecLib, (某些版本的) MKL, GCC 的 OpenMP 运行时,nvidia 的 Cuda (可能还有一些其他的),都是自行管理自己的内部线程池。在调用 `fork` 时，子进程中的线程池状态已损坏：线程池认为它有许多线程，而只有主线程状态已被 fork。有可能更改库，使它们在发生 fork 时检测，并在该情况下重新初始化线程池：我们对 OpenBLAS 执行了此操作（从 0.2.10 开始在 master 中合并），并且我们向 GCC 的 OpenMP 运行时提供了一个 `补丁 <https://gcc.gnu.org/bugzilla/show_bug.cgi?id=60035>`_ 
(尚未审查)。

但最终，真正的罪魁祸首是 Python 的 ``multiprocessing`` ，执行 ``fork`` 而不是执行 ``exec`` 来减少开始的和新使用的并行计算的 Python 进程的开销。但这这违反了 POSIX 标准，因而被一些软件编辑器（如苹果）拒绝认为在 Accelerate / vecLib 中缺乏 fork 安全是一个 bug。

在 Python 3.4 或以上版本中，现在可以配置 ``multiprocessing`` 决定使用 'forkserver' 或者 'spawn' 启动方法(而不是默认的 'fork' )来管理进程池。若要使用 scikit-learn 来解决此问题，你可以将 JOBLIB_START_METHOD 的环境变量设为 'forkserver' 。但是用户应该意识到使用 'forkserver' 方法会阻止 joblib.Parallel 调用在 shell 会话中交互定义的函数。

如果你直接使用 ``multiprocessing`` 的自定义代码而非通过调用 joblib 使用，你可以为你的程序全局启用 'forkserver' 模式：
在主脚本中插入以下说明::

    import multiprocessing

    # other imports, custom code, load data, define model...

    if __name__ == '__main__':
        multiprocessing.set_start_method('forkserver')

        # call scikit-learn utils with n_jobs > 1 here

你可以在 `multiprocessing文档 <https://docs.python.org/3/library/multiprocessing.html#contexts-and-start-methods>`_ 上找到更多新启动方法的默认值。

为什么不支持深度学习或强化学习/scikit-learn 中将会支持深度学习或强化学习吗?
--------------------------------------------------------------------------------------------------------------------------------------

深度学习和强化学习需要丰富的词汇来定义一个架构，深度学习还需要 GPU 来进行有效的计算。然而，这些都不符合 scikit-learn 的设计限制。因此，深度学习和强化学习目前已经超出了 scikit-learn 寻求实现的范围。

你可以找到更多关于gpu支持的信息 `Will you add GPU support?`_.

为什么我的pull请求没有得到注意?
-------------------------------------------------

scikit-learn 审查过程需要大量的时间，因此贡献者不应该因为 ``pull`` 请求缺乏回应或没有被审查而沮丧。我们非常关心第一次正确的使用，因为维护和以后的更改成本高昂。我们不会发布 "实验性" 代码, 所以我们所有的贡献将会立即得到大量使用，并且在最初的时候就应该是最高的质量。

除此之外，scikit-learn 在审查能力方面是有限的; 许多审稿人和核心开发人员都是利用自己的时间在 scikit-learn 工作。如果您的 ``pull`` 请求进展缓慢，可能是因为审阅者很忙，希望您能理解，并希望您不要因为这个原因而关闭您的 ``pull`` 请求或停止您的工作。

如何为整个执行设置一个统一的 ``random_state`` ?
------------------------------------------------------------------------

一般对于测试和复制，更为重要的是让整个执行由具有随机组件的算法中使用的伪随机数生成器的单个种子进行控制。Scikit-learn 不使用自己的全局随机状态;每当 RandomState 实例或整数随机种子不作为参数提供时，它依赖于类似的用法 :func:`numpy.random.seed` numpy 全局随机数种子。例如，要将执行的 numpy 全局随机状态设置为 42，可以在相应的脚本中执行以下操作::

    import numpy as np
    np.random.seed(42)

然而，全局随机状态在执行期间容易被其他代码修改。因此，确保可复制性的唯一方法是在每个地方传递 ``RandomState`` 实例，并确保估算器和交叉验证分隔符都具有其 ``random_state`` 参数集。
