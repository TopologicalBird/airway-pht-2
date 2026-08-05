# Supplementary Figures and Data
## Data scale information

<details>
<summary>List of $xyz$ resolutions (Click to view)</summary>

| ID   | x, y, z (mm) |
|------|--------------|
| 2  | 0.682, 0.682, 1.25 |
| 4  | 0.822, 0.822, 1.25 |
| 9  | 0.781, 0.781, 1.25 |
| 10 | 0.879, 0.879, 1.25 |
| 15 | 0.693, 0.693, 1.25 |
| 17 | 0.729, 0.729, 1.25 |
| 19 | 0.807, 0.807, 1.25 |
| 20 | 0.828, 0.828, 1.25 |
| 25 | 0.943, 0.943, 1.25 |
| 29 | 0.879, 0.879, 1.25 |
| 32 | 0.963, 0.963, 1.25 |
| 34 | 0.670, 0.670, 1.25 |
| 36 | 0.740, 0.740, 1.25 |
| 39 | 0.816, 0.816, 1.25 |
| 48 | 0.949, 0.949, 1.25 |
| 52 | 0.742, 0.742, 1.25 |
| 56 | 0.826, 0.826, 1.25 |
| 57 | 0.730, 0.730, 1.25 |
| 65 | 0.871, 0.871, 1.25 |

</details>


## Visualization of Projected Airways
### Full airway
We move from the front of the patient, then on the right hand side, and to the back of the patient.

https://github.com/user-attachments/assets/e9a33209-9b2b-42a5-90e3-ebcd738360d6

### Half airway
Left airway is mirrored to the right to mask directional information.

<table>
  <tr>
    <td>
      <video src="https://github.com/user-attachments/assets/bd9cd96e-56b4-4fb9-8544-8bdeb768839d" controls width="300"></video>
    </td>
    <td>
      <video src="https://github.com/user-attachments/assets/a8af40d8-9ae1-469d-9706-402c90dc4bdb" controls width="300"></video>
    </td>
  </tr>
</table>

### Differences between Seg1 and Seg2
Left: Seg1 (3dslicer)

Right: Seg2 (medpseg)

Patient ID: 19

Typically, Seg2 gives finer segmentation while Seg1 focuses on more central airways.

<table>
  <tr>
    <td>
      <img width="170" height="251" alt="rot_0_30" src="https://github.com/user-attachments/assets/f6f6b556-0125-47dc-941d-c18f4a6dacd8" />
    </td>
    <td>
      <img width="171" height="251" alt="rot_0_30" src="https://github.com/user-attachments/assets/5b59466d-ed8a-4852-8139-fe7430506eff" />
    </td>
  </tr>
</table>

There are some cases where Seg1 and Seg2 airways differ very much. In this example (patient ID: 56), the "hook" structure that characterizes left airway is hardly visible with Seg 1.

<table>
  <tr>
    <td>
      <img width="92" height="116" alt="rot_0_30_L" src="https://github.com/user-attachments/assets/29016e81-1669-4a90-a5a9-5751ceddfc32" />
    </td>
    <td>
      <img width="70" height="116" alt="rot_0_30_L" src="https://github.com/user-attachments/assets/c5893686-7fe6-43ed-8487-3f40894b35af" />
    </td>
  </tr>
</table>



## PCA Plots
### Full airway with Projection PHT (left) and Direct PHT (right)
<table>
  <tr>
    <td>
      <img width="989" height="990" alt="proj_full" src="https://github.com/user-attachments/assets/715eb564-e40f-466b-b0a3-19cc01098e14" />
    </td>
    <td>
      <img width="989" height="990" alt="direct_full" src="https://github.com/user-attachments/assets/094563f0-ed46-418e-8bd2-258128149c06" />
    </td>
  </tr>
</table>

Both Projection PHT and Direct PHT yield similar distributions with different vectorization parameters and segmentation methods. We quantitatively evaluated the similarity using RV coefficients. With both Projection PHT and Direct PHT, RV coefficients between the same segmentation methods were larger than 0.9, highlighting the robustness of our methods against parameter choice. RV coefficients between different segmentation methods were around 0.7. 

### Half airway with Projection PHT (left) and Direct PHT (right)
<table>
  <tr>
    <td>
      <img width="989" height="790" alt="proj_half" src="https://github.com/user-attachments/assets/5ce589ab-4edd-4fc5-8f54-b3ba2e8feab2" />
    </td>
    <td>
      <img width="989" height="790" alt="direct_half" src="https://github.com/user-attachments/assets/ede28972-7bc9-47d2-8db2-aa5efe0e59c3" />
    </td>
  </tr>
</table>

With Projection PHT, we can capture the difference between left and right airways. The separation is less clear in Direct PHT, but we can still see the existence of differences between right and left airways.

## Feature contribution analysis
### Projection PHT
<table>
  <tr>
    <td>
      <img width="530" height="393" alt="pc2-seg1" src="https://github.com/user-attachments/assets/0ba7f789-bbc6-413e-bd79-70b78c00d16c" />
    </td>
    <td>
      <img width="538" height="393" alt="seg1-logreg" src="https://github.com/user-attachments/assets/b9628ca8-f24f-4b89-b466-c9964ed7489e" />
    </td>
    <td>
      <img width="538" height="393" alt="seg2-logreg" src="https://github.com/user-attachments/assets/8ac0d4ce-ac68-4651-816a-e74e237f17e8" />
    </td>
  </tr>
</table>

(Left figure) L/R separation of Seg1 airways using Projection PHT seems very clear. PC2 is the main component separating L/R. Here, we visualize the eigenvector corresponding to PC2. $x$ axis is the PHT direction and $y$ axis is the projection direction.
(Middle and right figures) L/R classification model coefficient of Seg1 (middle) and Seg2 (right) airways by Projection PHT.
Reasonably, all the three figures have similar patterns.
### Direct PHT
<table>
  <tr>
    <td>
      <img width="530" height="456" alt="pc2-seg1" src="https://github.com/user-attachments/assets/49c708c4-55e6-4ff1-86ef-a969ef282425" />
    </td>
    <td>
      <img width="538" height="456" alt="seg1-logreg" src="https://github.com/user-attachments/assets/f969bc1e-d316-4c7c-8b91-a7e37b9f0f3d" />
    </td>
    <td>
      <img width="538" height="456" alt="seg2-logreg" src="https://github.com/user-attachments/assets/7817f89c-44e3-469d-a4a7-6353a60529e4" />
    </td>
  </tr>
</table>
