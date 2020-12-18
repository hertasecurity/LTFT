
# Long-Term Face Tracking for Crowded Video-Surveillance Scenarios

![System scheme](images/system_scheme.png)

**Authors:** Germán Barquero, Carles Fernández and Isabelle Hupont

> Most current multi-object trackers focus on short-term tracking, and are based on deep and complex systems that do not operate in real-time, often making them impractical for video surveillance. In this paper, we present a long-term multi-face tracking architecture conceived for working in crowded contexts, particularly unconstrained in terms of movement and occlusions, and where the face is often the only visible part of the person. Our system benefits from advances in the fields of face detection and face recognition to achieve long-term tracking. It follows a tracking-by-detection approach, combining a fast short-term visual tracker with a novel online tracklet reconnection strategy grounded on face verification. Additionally, a correction module is included to correct past track assignments with no extra computational cost. We present a series of experiments introducing novel, specialized metrics for the evaluation of long-term tracking capabilities and a video dataset that we publicly release. Findings demonstrate that, in this context, our approach allows to obtain up to 50% longer tracks than state-of-the-art deep learning trackers.


---

## Table of Contents


- [Videos](#Videos)
- [Annotations](#Annotations)
- [References](#Bibtex)



---

## Videos

### **Summary**

| Video | Length  | FPS | Frames  | Resolution  | Scenario  | Subjects  |
|---    |---      |---  |---      |---          |---        |---        |
| **IJCB paper** |   |   |   |   |   |   |
| Choke1 | 1' 24" | 30 | 2526 |800x600|indoor|24|
| Choke2 |1' 11"| 30|2139|800x600|indoor|26|
| Street |1' 8"|30|2042|1920x1080|outdoor|31|
| Sidewalk |27"|24|648|1920x1080|outdoor|34|
| Bengal |40"|25|1000|1920x1080|outdoor|36|
| **T-BIOM extension** |   |   |   |   |   |   |
| Terminal1 |1' 18"|30|2341|1920x1080|indoor|148|
| Terminal2 |1' 15"|30|2240|1920x1080|indoor|140|
| Terminal3 |26"|30|771|1920x1080|indoor|59|
| Terminal4 |35"|30|1070|1920x1080|indoor|126|
| Shibuya |30"|25|892|3840x2160|outdoor|91|

<br>

### **Instructions - IJCB Videos**

#### > Choke1
1) Download <a href="https://zenodo.org/record/815657/files/P2E_S5.tar.xz" target="_blank">the P2E_S5 video</a> from the <a href="http://arma.sourceforge.net/chokepoint/" target="_blank">ChokePoint dataset</a>.
2) Then, concatenate frames from P2E_S5_C1.2, P2E_S5_C1.1 and P2E_S5_C1.3, in this specific order, to generate <i>Choke1</i>.


#### >  Choke2
1) Download <a href="https://zenodo.org/record/815657/files/P2L_S5.tar.xz" target="_blank">the P2L_S5 video</a> from the <a href="http://arma.sourceforge.net/chokepoint/" target="_blank">ChokePoint dataset</a>.
2) Then, concatenate frames from P2L_S5_C1.2, P2L_S5_C1.1 and P2L_S5_C1.3, in this specific order, to generate <i>Choke2</i>.


#### >  Street
1) Download <a href="https://www.youtube.com/watch?v=6NBwbKMyzEE" target="_blank">this video</a> from youtube at 30 FPS.
2) Then, cut it from the beginning (frame 0) to frame 2041.


#### >  Sidewalk
1) Download <a href="https://www.youtube.com/watch?v=UgUC_IY7rMw" target="_blank">this video</a> from youtube at 24 FPS, its original resolution.
2) Cut it from frame 140 to frame 1436.
3) Keep only even frames to double the speed of the video while keeping the same FPS (original video was recorded in slow-motion).


#### >  Bengal
1) Download <a href="https://www.youtube.com/watch?v=oMJyrvHSGqY" target="_blank">this video</a> from youtube at 25 FPS.
2) Then, cut it from frame 8475 to frame 9474.

<br>

### **Instructions - T-BIOM Videos**

The four terminal videos were extracted from the <a href="https://www.youtube.com/watch?v=SqZWZTu1veA" target="_blank">same video</a>, at 30FPS and a resolution of 1080p.

#### >  Terminal1
From frame 2400 to frame 4740, both included.

#### >  Terminal2
From 00:23:37 to 00:24:52.

#### >  Terminal3
From 00:19:49 to 00:20:15.

#### >  Terminal4
From 00:06:45 to 00:07:21.


#### >  Shibuya
1) Download <a href="https://www.youtube.com/watch?v=8ig8yLeV5dU" target="_blank">this video</a> from youtube at 25 FPS and 4K resolution.
2) Then, cut it from 00:04:50 to 00:05:20.
---

## Annotations
Annotations can be found in the folder <b>annotations</b>, in this project root. The annotation files follow this structure:

```
#frames
#num_frame #num_detections #det_1 #det_2 ... #det_n
#num_frame #num_detections #det_1 #det_2 ... #det_m
...
```
where each detection (#det_1, #det_2, etc) corresponds to:
```
#det_id #pos_x #pos_y #width #height #face #confidence
```

*Example:* 5 frames, 3 unique identities (IDs 1, 2, 3)
```
5
0 2 1 1463.76 363.048 68.4058 83.2624 1 0.999573 2 1225.19 481.665 28.6068 36.4942 1 0.987961
1 2 1 1465.67 364.609 67.5731 85.1121 1 0.999656 3 723.033 455.345 82.4843 125.746 1 0.994548 
2 1 1 1463.81 365.749 71.8081 89.0789 1 0.999537
3 2 1 1462.78 368.577 69.2908 86.1318 1 0.999626 2 1226.64 481.859 29.2073 38.1166 1 0.990422
4 1 1 1462.84 371.797 68.8722 84.7612 1 0.999622
```
> <i>#face</i>: flag used to mark detections corresponding to false positives or detections with several faces inside.<br>
> <i>#confidence</i>: probability value inferred by the face detector.


---

## References

If you use this work, please cite us:

> G. Barquero, C. Fernández, I. Hupont. "Long-Term Face Tracking for Crowded Video-Surveillance Scenarios". International Joint Conference on Biometrics. 2020

```
@article{barquero2020long,
  title={Long-Term Face Tracking for Crowded Video-Surveillance Scenarios},
  author={Barquero, Germ{\'a}n and Fern{\'a}ndez, Carles and Hupont, Isabelle},
  journal={International Joint Conference on Biometrics},
  year={2020}
}
```


If you use the ChokePoint videos in your work, please also cite:


> Y. Wong, S. Chen, S. Mau, C. Sanderson, B.C. Lovell. "Patch-based probabilistic image quality assessment for face selection and improved video-based face recognition". In CVPR 2011 Workshops (pp. 74-81), IEEE. June 2011
---

