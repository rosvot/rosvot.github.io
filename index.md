# Robust Singing Voice Transcription Serves Synthesis

<!-- Google tag (gtag.js) -->
<!-- <script async src="https://www.googletagmanager.com/gtag/js?id=G-86MF0006K1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-86MF0006K1');
</script> -->

## Abstract

Note-level Automatic Singing Voice Transcription (AST) converts singing recordings into note sequences, facilitating the automatic annotation of singing datasets for Singing Voice Synthesis (SVS) applications. Current AST methods, however, struggle with accuracy and robustness when used for practical annotation. This paper presents ROSVOT, the first robust AST model that serves SVS, incorporating a multi-scale framework that effectively captures coarse-grained note information and ensures fine-grained frame-level segmentation, coupled with an attention-based pitch decoder for reliable pitch prediction. We also established a comprehensive annotation-and-training pipeline for SVS to test the model in real-world settings. Experimental findings reveal that the proposed model achieves state-of-the-art transcription accuracy with either clean or noisy inputs. Moreover, when trained on enlarged, automatically annotated datasets, the SVS model outperforms its baseline, affirming the capability for practical application. 


## SVS Results of Different Ratios of Pseudo Annotations

We train ROSVOT with M4Singer dataset and utilize which to annotate and generate the pseudo annotations of dataset $D_1$. Pseudo annotations with different ratios are mixed into $D_1$ to train the SVS model, RMSSinger. The inference is performed on the test set of $D_1$.

* **Models**:
  * **GT**: Ground Truth samples generated with the vocoder.
  * **100%D1**: the SVS model trained with 100% of the real annotations.
  * **50%D1**: trained with 50% of the real and 50% of the pseudo annotations.
  * **10%D1**: 10% real and 90% pseudo.
  * **5%D1**: 5% real and 95% pseudo. 
  * **0%D1**: 100% pseudo annotations. 

1. \<breath> 如 果 那 两 个 字 没 有 颤 抖 \<breath> 我 不 会 发 现 我 难 受 \<breath> 怎 么 说 出 口 \<silence>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/1.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>100%D1</th>
            <th>50%D1</th>
            <th>10%D1</th>
            <th>5%D1</th>
            <th>0%D1</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/d1_100/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_50/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_10/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_5/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_0/1.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>
2. 再 一 次 沾 染 你 \<breath> 若 生 命 \<breath> 如 过 场 电 影 \<breath>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/2.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>100%D1</th>
            <th>50%D1</th>
            <th>10%D1</th>
            <th>5%D1</th>
            <th>0%D1</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/d1_100/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_50/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_10/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_5/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_0/2.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>
3. 能 够 握 紧 的 就 别 放 了 \<breath> 能 够 拥 抱 的 就 别 拉 扯 \<breath> 时 间 着 急 地 \<breath>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/3.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>100%D1</th>
            <th>50%D1</th>
            <th>10%D1</th>
            <th>5%D1</th>
            <th>0%D1</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/d1_100/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_50/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_10/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_5/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_0/3.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>
4. 去 寻 找 遗 失 了 的 思 念 \<breath> 如 果 你 在 眼 前 \<breath> 我 会 让 你 看 见 \<silence>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/4.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>100%D1</th>
            <th>50%D1</th>
            <th>10%D1</th>
            <th>5%D1</th>
            <th>0%D1</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/d1_100/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_50/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_10/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_5/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/d1_0/4.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

## SVS Results of Expanding Datasets

We use MFA and the same ROSVOT trained with M4Singer to re-align and re-annotate OpenSinger, a multi-singer dataset designed for training vocoders which is without note annotations. We use M4Singer as the base training set and gradually involve dataset $D_1$ and OpenSinger to see the improvement of the SVS model. The inference is performed on the test set of $D_1$ and M4Singer. However, model **M4** is only tested on M4Singer (sample 5 and 6) since we don't investigate SVS model's generalization capabilities here.

* **Models**:
  * **GT**: Ground Truth samples generated with the vocoder.
  * **M4**: the SVS model trained with M4Singer, as the baseline.
  * **M4+100%D1**: trained with M4Singer and dataset $D_1$ with 100% real annotations.
  * **M4+0%D1**: trained with M4Singer and dataset $D_1$ with 0% real annotations (100% pseudo annotations).
  * **M4+0%D1+OP**: A large version of RMSSinger, trained with M4Singer and dataset $D_1$ with 0% real annotations and OpenSinger.

1. \<breath> 如 果 那 两 个 字 没 有 颤 抖 \<breath> 我 不 会 发 现 我 难 受 \<breath> 怎 么 说 出 口 \<silence>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/1.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_2/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/1.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/1.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

2. 再 一 次 沾 染 你 \<breath> 若 生 命 \<breath> 如 过 场 电 影 \<breath>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/2.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_2/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/2.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/2.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

3. 能 够 握 紧 的 就 别 放 了 \<breath> 能 够 拥 抱 的 就 别 拉 扯 \<breath> 时 间 着 急 地 \<breath>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/3.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_2/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/3.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/3.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

4. 去 寻 找 遗 失 了 的 思 念 \<breath> 如 果 你 在 眼 前 \<breath> 我 会 让 你 看 见 \<silence>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/4.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_2/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/4.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/4.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

5. 我 想 唱 一 首 歌 给

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/5.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4</th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_1/5.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_2/5.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/5.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/5.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

6. 却 是 下 落 不 详 \<breath> 心 好 \<silence> 空 荡 \<breath>

    <table style='width: 20%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/6.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>M4</th>
            <th>M4+100%D1</th>
            <th>M4+0%D1</th>
            <th>M4+0%D1+OP</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/exp_1/6.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_2/6.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_3/6.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/exp_4/6.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

## SVS with English Transcriptions

We use MFA and the same ROSVOT trained with M4Singer to re-align and re-annotate a small English singing dataset, $D_2$. We finetune the instance *M4+0%D1+OP* in the previous section using the Enligh singing dataset to test the cross-lingual annotation capability of ROSVOT. The inference is performed on English transcriptions.

* **Models**:
  * **GT**: Ground Truth samples generated with the vocoder.
  * **RMSSinger**: a large version, pre-trained with M4Singer + $D_1$ + OpenSinger and finetuned with $D_2$. 

1. I wouldn't change a thing about it

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
            <th>RMSSinger</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/7.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/cross/7.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>

2. They've all been said before you know \<breath> so why don't we \<breath> just play pretend \<breath>

    <table style='width: 100%;'>
        <thead>
        <tr>
            <th></th>
            <th>GT</th>
            <th>RMSSinger</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <th scope="row">wav</th>
            <td><audio controls="" ><source src="resources/audio/gt/8.wav" type="audio/wav"></audio></td>
            <td><audio controls="" ><source src="resources/audio/cross/8.wav" type="audio/wav"></audio></td>
        </tr>
        </tbody>
    </table>
