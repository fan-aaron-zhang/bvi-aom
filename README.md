BVI-AOM Database
================
A Training Database for Video Compression Research Adapted to Alliance for Open Media's (AOM) Needs

[[Database Download]](http://download.opencontent.netflix.com.s3.amazonaws.com/index.html?prefix=bvi_aom_dataset/)  [[arXiv]](https://arxiv.org/abs/2408.03265)

AUTHORS
=========================
Jakub Nawała<sup>1</sup>, Yuxuan Jiang<sup>1</sup>, Fan Zhang<sup>1</sup>, Xiaoqing Zhu<sup>2</sup>, Joel Sole<sup>2</sup> and David Bull<sup>1</sup>

<sup>1</sup>University of Bristol, UK  
<sup>2</sup>Netflix Inc., US

CITATION
====================
@article{nawala2024bvi,<br />
  title={BVI-AOM: A New Training Dataset for Deep Video Compression Optimization},  
  author={Nawa{\l}a, Jakub and Jiang, Yuxuan and Zhang, Fan and Zhu, Xiaoqing and Sole, Joel and Bull, David},<br />
  journal={arXiv preprint arXiv:2408.03265},<br />
  year={2024}<br />
}

DATASET CONSTRUCTION
====================
There are 956 video sequences in this dataset. These have been generated from 239 unique 4k (3840x2176 px) source sequences.
The 4k sequences have been spatially down-sampled to three other resolutions: 1920x1088 px, 960x544 px, and 480x272 px. (Please
note that that vertical resolution has been intentionally made to be a multiple of 64.) Down-sampling was performed using the
Lanczos-3 filter. The implementation of the filter was taken from AVM's (AOM Video Model) GitLab repository. Specifically,
we used the code at tag "research-v3.1.0" found under the following link: https://gitlab.com/AOMediaCodec/avm/-/tree/research-v3.1.0/tools/lanczos.

Each sequence in the dataset has a filename generated using the following file naming convention:
    <R><sequence_name>_<width>x<height>_<framerate>fps_<bit_depth>bit_<chroma_sampling>,

where <R> is a single letter corresponding to a resolution class: A (3840x2176 px), B (1920x1088 px), C (960x544 px), and D (480x272 px);
<sequence_name> is an alphanumeric sequence identifing a given source sequence (e.g., MidnightSun);
<width> and <height> represent video width and height in pixels (e.g., 480x272);
<framerate> corresponds to source video's framerate (e.g., 50);
<bit_depth> represents video's bit depth (10 for all videos in this dataset);
<chroma_sampling> identifies what chroma sampling scheme is used (420 for all videos in this dataset).

Importantly, each sequence in this dataset is 64-frame long and does NOT contain any scene cuts. This means that most sequences in this
dataset have been generated by extracting 64-frame long fragments from longer sequences.

All sequences in this dataset have been losslessly compressed using the h.264 codec. Please use FFmpeg (https://ffmpeg.org/) to
extract raw video data from each file. See below for an example FFmpeg call:

    $ ffmpeg.exe -i DAncientThoughtS14_480x272_24fps_10bit_420_x264_compressed.mkv DAncientThoughtS14_480x272_24fps_10bit_420_x264_compressed.yuv

VIDEO PROPERTIES
================
Resolutions and Scanning Format: From 272p to 2176p, progressively scanned
Chroma Sampling: 4:2:0
Bit Depth: 10 bit
Audio: No audio
File Size: 124 GB (before ZIP compression)
Dynamic range: Standard Dynamic Range (SDR)

CONTACT
=======
In case of any issues with this dataset, please get in touch with us by sending a message to the following email addresses:

    jakub.nawala@bristol.ac.uk

    yuxuan.jiang@bristol.ac.uk
    
    fan.zhang@bristol.ac.uk
    
    dave.bull@bristol.ac.uk

COPYRIGHT & PERMISSION NOTICE
=============================
This dataset is a collection of video sequences sourced from various sources. The following is a list of those sources:
1) Videvo Free Stock Video Footage set (Stock footage provided by Videvo, downloaded from https://www.videvo.net)
2) IRIS32 Free 4K Footage set (https://www.youtube.com/channel/UCjJee-JAzoRRH5T0wqe7_tw)
3) Harmonics database (https://www.harmonicinc.com/)
4) BVI-Texture database (https://data.bris.ac.uk/data/dataset/1if54ya4xpph81fbo1gkpk5kk4)
5) MCML 4K video quality database (http://mcml.yonsei.ac.kr/downloads/4kuhdvideoquality)
6) BVI-HFR database (https://data.bris.ac.uk/data/dataset/ca830349ffcba535c2045ca9d2304faf)
7) SJTU 4K video database (http://medialab.sjtu.edu.cn/web4k/index.html)
8) LIVE-Netflix database (https://live.ece.utexas.edu/research/LIVE_NFLXStudy/nflx_index.html)
9) Mitch Martinez Free 4K Stock Footage set (https://mitchmartinez.com/free-4k-red-epic-stock-footage/)
10) Dareful Free 4K Stock Video data set (https://www.dareful.com/)
11) MCL-V database (http://mcl.usc.edu/mcl-v-database/)
12) MCL-JCV database (http://mcl.usc.edu/mcl-jcv-dataset/)
13) Netflix Chimera (https://www.netflix.com/gb/title/80015538)
14) TUM HD databases (https://www.ei.tum.de/en/ldv/research/videolab/data-sets-downloads/tum-1080p50-data-set/)
15) The American Society of Cinematographers - Standard Evaluation Material II (StEM2) (https://theasc.com/society/stem2)
16) SVT Open Content Video Test Suite 2022 - Natural Complexity (https://media.xiph.org/svt/2022/)
17) CableLabs 4K Video (https://www.cablelabs.com/4k)

When using sequences from source no. 9) [sequences FireS18Mitch, FireS21Mitch, FireS71Mitch, SmokeS45Mitch, WaterS65Mitch, and WaterS81Mitch],
please credit and link to www.mitchmartinez.comÂ from any published results.

When using the FlagShootTUMSVT sequence from source no. 14), please observe the following copyright notice: "Individuals and organizations
extracting sequences from this archive agree that the sequences and all intellectual property rights therein remain the property of
Sveriges Television AB (SVT), Sweden. These sequences may only be used for the purpose of developing, testing and presenting technology standards.
SVT makes no warranties with respect to the materials and expressly disclaim any warranties regarding their fitness for any purpose."

When using sequences from source no. 17) [see sequences with the CableLabs watermark in the lower right-hand corner], plesase observe the following
copyright notice:
    "This website is dedicated to providing video content for free under the Creative Commons License linked below.
    It is intended to showcase cutting edge filming techniques, ultra high resolution, expanded color spaces, high
    dynamic range, and more. Consumers, distributors, and vendors can take advantage of this content for demonstrations,
    testing, and entertainment purposes.
    
    These works are licensed under a Creative Commons Attribution-NonCommercial-NoDerivs 3.0 Unported License
    (http://creativecommons.org/licenses/by-nc-nd/3.0/deed.en_US)."

When using sequences from source no. 15) [see sequences with names starting from "AscStem"], please observe licensing terms provided at the bottom
of this README file (see the "StEM2 LICENSING TERMS").

In addition to specific per-source copyright restrictions (outlined above), for all sequences in the BVI-AOM dataset, the University of Bristol
has been given permission by respective copyright holders to use the following copyright notice:
    The database has been compiled by the University of Bristol, Bristol, UK, comprising sequences originally generated by various sources.
    All intellectual property rights remain with the originators of each sequence. The material shall only be used for developing future
    video coding standards, for training or performance evaluation of test models in JVET and Alliance for Open Media, and the subsequent
    standardization project, and for the relational parent body activities. This copyright and permission notice shall be duplicated
    whenever the data is copied or distributed. The material cannot be distributed with charge. The University of Bristol makes no
    warranties with respect to the material and expressly disclaims any warranties regarding its fitness for any purpose. Unless
    the above conditions are agreed to by the recipient, no permission is granted for any use, copying, and distribution of the data.
    By using the database and sequences, the user agrees to the conditions of this copyright and disclaimer.

StEM2 LICENSING TERMS
=====================
By downloading any of these files, you agree to the terms of this license:

ASWF Digital Assets License v1.1

StEM2 -- Copyright 2022 -- American Society of Cinematographers -- All rights reserved.

Redistribution and use of these digital assets, with or without modification, solely for education, training, research,
software and hardware development, performance benchmarking (including publication of benchmark results and permitting
reproducibility of the benchmark results by third parties), or software and hardware product demonstrations, are permitted
provided that the following conditions are met:

    1. Redistributions of these digital assets or any part of them must include the above copyright notice, this list of
       conditions and the disclaimer below, and if applicable, a description of how the redistributed versions of the
       digital assets differ from the originals.
    2. Publications showing images derived from these digital assets must include the above copyright notice.
    3. The names of copyright holder or the names of its contributors may NOT be used to promote or to imply endorsement,
       sponsorship, or affiliation with products developed or tested utilizing these digital assets or benchmarking
       results obtained from these digital assets, without prior written permission from copyright holder.
    4. The assets and their output may only be referred to as the Asset Name listed above, and your use of the Asset Name
       shall be solely to identify the digital assets. Other than as expressly permitted by this License, you may NOT use
       any trade names, trademarks, service marks, or product names of the copyright holder for any purpose.

DISCLAIMER: THESE DIGITAL ASSETS ARE PROVIDED BY THE COPYRIGHT HOLDER "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING,
BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE, ARE DISCLAIMED. IN NO EVENT
SHALL COPYRIGHT HOLDER BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING
IN ANY WAY OUT OF THE USE OF THESE DIGITAL ASSETS, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
