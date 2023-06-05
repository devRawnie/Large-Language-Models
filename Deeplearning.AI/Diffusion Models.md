# Diffusion Model

## Neural network

Needs to learn
- Fine Details
- General Outlines

> SPRITE IMAGE : A collection of images put into a single image

Noising Process - Inspired by diffusion in physics

- Add different noise levels to the training data of sprites
- Neural network learns to take different noisy images and turn them back into sprites

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/fa0991b2-c24e-4007-940a-ac94f231d042)

- Neural network predicts noise instead of a sprite
- It will remove some noise itereatively at each step, until we get a good result
