# Supplementary Figures and Data
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
      <img width="989" height="1589" alt="proj_full" src="https://github.com/user-attachments/assets/fa746cf5-a054-41cc-8d75-323503410de4" />
    </td>
    <td>
      <img width="989" height="1589" alt="direct_full" src="https://github.com/user-attachments/assets/c95cffd4-892d-408c-bb5c-62d2748e1d3d" />
    </td>
  </tr>
</table>

Both Projection PHT and Direct PHT yield similar distributions with different vectorization parameters and segmentation methods. We quantitatively evaluated the similarity using RV coefficients. With both Projection PHT and Direct PHT, RV coefficients between the same segmentation methods were larger than 0.9, highlighting the robustness of our methods against parameter choice. RV coefficients between different segmentation methods were around 0.7. 

### Half airway with Projection PHT (left) and Direct PHT (right)
<table>
  <tr>
    <td>
      <img width="989" height="790" alt="proj_half" src="https://github.com/user-attachments/assets/a77dafb7-4a2e-46a3-8f24-0bd35d14ec05" />
    </td>
    <td>
      <img width="989" height="790" alt="direct_half" src="https://github.com/user-attachments/assets/ee767b5a-205b-4816-bafb-36859a5f6fe2" />
    </td>
  </tr>
</table>

With Projection PHT, we can capture the difference between left and right airways. The separation is less clear in Direct PHT, but we can still see the existence of differences between right and left airways.

## Feature contribution analysis
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
