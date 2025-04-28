# COMPARISON_OF_GAN_LOSS_FUNCTIONS

Generative Adversarial Networks (GANs) have revolutionized the landscape of generative modeling. By setting two neural networks — a generator and a discriminator — in a competitive framework, GANs have made it possible to synthesize images, music, and even text that closely mimic real-world data. In this article, we thoroughly explore three influential GAN variants: Least Squares GAN (LS-GAN), Wasserstein GAN (WGAN), and Wasserstein GAN with Gradient Penalty (WGAN-GP). Their effectiveness is assessed using the RetinaMNIST dataset, with evaluation metrics including the Inception Score (IS) and Fréchet Inception Distance (FID) to uncover their individual strengths and differences.

The RetinaMNIST dataset, part of the broader MedMNIST collection, is specifically tailored for medical imaging challenges. Its notable features are:

Image Resolution: 28×28 pixels

Preprocessing: Pixel intensities normalized within the range [-1, 1]

Image Type: Grayscale with a single channel (28×28×1)
![image](https://github.com/user-attachments/assets/51439e69-003b-4ff9-bc10-245a405a8840)


1. Least Squares GAN (LS-GAN)
LS-GAN modifies the conventional GAN loss by introducing a least squares objective, offering several benefits:

Smoother Gradient Flow: Mitigates the vanishing gradient problem, leading to more stable training.

Better Image Quality: Produces sharper and more detailed outputs due to the improved gradient behavior.

Network Design: Commonly built with several convolutional layers and batch normalization, enhancing feature extraction and image synthesis.

2. Wasserstein GAN (WGAN)
WGAN introduces a fundamental shift by replacing the standard binary classification loss with the Wasserstein distance, a meaningful metric for comparing probability distributions:

Wasserstein Loss: Accurately reflects how closely the generated data distribution matches the real data.

Training Robustness: Generally achieves greater stability and is less susceptible to problems like mode collapse.

Critic Architecture: Unlike traditional discriminators, WGAN critics omit batch normalization to uphold Lipschitz continuity essential for Wasserstein computations.

3. Wasserstein GAN with Gradient Penalty (WGAN-GP)
WGAN-GP extends WGAN by incorporating a gradient penalty, offering key improvements:

Maintaining Lipschitz Continuity: Gradient penalty replaces aggressive weight clipping, promoting smoother training.

Enhanced Stability: Although computationally heavier, it results in more reliable convergence.

Architectural Design: Similar to WGAN, but with gradient regularization integrated into the loss computation.

Evaluation Metrics
Evaluating GANs is inherently difficult, but two widely used metrics help:

Inception Score (IS): Measures the quality and diversity of generated samples using a pre-trained classifier. A higher IS indicates clearer and more varied images, although its reliability depends on the classifier’s alignment with the dataset.

Fréchet Inception Distance (FID): Assesses how similar real and generated image distributions are by comparing feature-level statistics from a pre-trained model. Lower FID values suggest generated samples are closer to real data in quality and variety.

### Experimental Findings
Performance on RetinaMNIST was summarized as follows:

LS-GAN: IS ≈ 1.00, FID ≈ 263.34

WGAN: IS ≈ 1.00, FID ≈ 263.34

WGAN-GP: IS ≈ 1.00, FID ≈ 333.25
![image](https://github.com/user-attachments/assets/e74e8a5e-8f1a-4274-9175-7479276d596b)
![image](https://github.com/user-attachments/assets/e374fc3b-6ff7-4a29-bff2-f4109b9839eb)
![image](https://github.com/user-attachments/assets/ed8a5e12-5f69-4398-addb-bb5e99f11943)



Through a detailed comparison, LS-GAN emerged as the most effective method for generating retinal images from the RetinaMNIST dataset. Although WGAN and WGAN-GP offer theoretical benefits, especially regarding distributional learning, LS-GAN demonstrated better practical performance in this task, as reflected in its lower FID score. This study highlights the crucial balance between theoretical advances and practical training techniques in advancing generative modeling.

