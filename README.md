# Thesis
## Adversarial Attacks on Monocular Depth Estimation
### Abstract
**Background**: Autonomous driving is inevitable and needs to be achieved safely. To accomplish this, adversarial attacks must be anticipated and overcome. Wei et al. conducted the latest study on "Physical Adversarial Attacks and Defenses in Computer Vision," which included a segment on Optical adversarial attacks. That segment is the topic that is most closely related to this thesis. However, this thesis will focus on optical illusions, which was not addressed in their research. The adversarial attack in question is an untargeted, evasive, black box attack. 

**Aim**: This thesis will discover how ready the current state-of-the-art technology is against a certain type of adversarial attack. The objective is to find out whether the current state-of-the-art technology can detect optical illusions (i.e.: fake bridge paintings painted on walls) and what is the best way to avoid it.

**Materials and Methods**: The strategy employed is to leverage DIFFNet, that is a self-supervised structure from motion algorithm, to output a depth estimation map to counter act the attack and detect a painting and not an actual tunnel. To check whether DIFFNet can help with this detection, TensorFlow Lite Model Maker is used to create a bounding box output with either a “Painting” or “Real_bridge” class on the image output processed by DIFFNet. The accuracy is then compared with TensorFlow Lite Model Maker run on an image that is not processed through DIFFNet. Six strategies were employed to determine the best one to mitigate the adversarial attack. Model maker object detection was used to calculate the metrics of detecting a fake painting, with the input changing for each strategy. The strategies consist of manipulating the input of the model maker by combining DIFFNet’s output with the original image.

**Results**: Strategy number 5, which is adding a grayscale image of the DIFFNet output as a fourth channel to the original image as an input to the classification model, outperforms the benchmark. The loss is 35% better than the benchmark, and the accuracy is 90% better than the benchmark.

**Conclusion**: The best strategy to avoid adversarial attacks in the form of optical illusions is to convert DIFFNet’s output into grayscale and adding it as a 4th channel before checking the image for adversarial attacks.



