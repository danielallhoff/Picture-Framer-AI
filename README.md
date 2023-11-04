# Picture-Framer-AI

## Introduction
This project addresses a genuine need for businesses specializing in the sale of various types of paintings and framed images. To simplify the selection process for clients, we propose a method that compares only the corners of the images, enabling them to make informed decisions between different options.
By harnessing the power of **Deep Learning**, integrated within a user-friendly mobile application, users can effortlessly capture a photo, select a frame, and seamlessly apply it to their chosen image. This approach allows for a quick and comprehensive preview, ultimately enhancing the overall value of the business.
For the present implementation, a single applicable picture design has been chosen to streamline the problem-solving process. However, the incorporation of additional designs is feasible by appending a label, indicating the specific picture type to be applied. Leveraging the transfer learning technique, we can significantly reduce the amount of initial data required for training, thereby streamlining the development process.


## Development
For this undertaking, the **pix2pix** model was employed, a conditional generative adversarial network (cGAN) commonly utilized for image translation tasks. As this model necessitates a substantial volume of paired photos, manually capturing such data with a camera can be exceedingly challenging. To circumvent this limitation, a simulated environment was created within the Unity video game development program.

This simulated environment facilitated the **procedural generation** of numerous examples, thereby enabling the network to assimilate the process of transforming frameless images into framed ones. This approach significantly streamlined the data generation process, allowing the network to learn more effectively within the specified parameters.

![In a single picture](https://raw.githubusercontent.com/danielallhoff/Picture-Framer-AI/master/raw_images/synthetic_transformation.PNG)


In this simulation, we specifically manipulated the angle and distance to the image, incorporating variations in the frame's size to ensure robust generalization. By meticulously adjusting these parameters, we aimed to enhance the network's ability to accurately translate images under diverse conditions.

To validate the model's efficacy and assess its success in achieving accurate generalization, we conducted a real-world test using an image featuring an authentic background. This real-world validation process served as a crucial step in evaluating the network's performance and its capability to seamlessly integrate with genuine environmental settings.


## Results

When trying the first training with only 10 samples of background and picture images, the results were really bad.

![In a single picture](https://raw.githubusercontent.com/danielallhoff/Picture-Framer-AI/master/raw_images/first_results/0.png)

However, as I started recollecting more backgrounds and pictures, the results on the synthetic images started to being promising. For example:

![In a single picture](https://raw.githubusercontent.com/danielallhoff/Picture-Framer-AI/master/raw_images/synthetic_test_transformation.jpg)

Finally, after the training on synthetic data, I recorded some real samples and tested the performance on real world data. The best result I got is:

![In a single picture](https://raw.githubusercontent.com/danielallhoff/Picture-Framer-AI/master/raw_images/real_test_transformation.PNG)



## Conclusions
At first, when I trained for a while, I didn't get good results. It seems that between the overfitting that has occurred and the little variability of background / image (I used at first only 10 images for the background and 10 for the image approximately) I have not managed to get good results. Moreover, there is a big gap between real and synthetic data. As a result, when trying it with images of the real world, the results were poor. One posible solution is the **combination of synthetic and real data pairs to the pix2pix model**.The problem is the time required to prepare the real data pairs. Another solution, would be working on loosen the gap between synthetic and real data. 



