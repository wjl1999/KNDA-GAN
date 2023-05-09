# KNDA-GAN
Open codes for KNDA-GAN
# Code
## Train
python train.py --dataroot yourDataroot --name nameThisTraining \
--batch_size 4 --dataset_mode approximateAligned --direction AtoB \
--gan_mode lsgan --gpu_ids 0 \
  --lambda_A 10.0 --lambda_B 10.0 --lambda_identity 0.5\
  --lambda_L1 100.0 --lambda_L2 3.0 --lambda_LG 20.0 \
   --model KNDA --n_epochs 50 --n_epochs_decay 50\
    --norm instance --preprocess None \
    --input_nc 1 --output_nc 1 \
    --display_port 8089  --display_env training --pool_size 0 \
    --no_flip

## Test
python test.py --dataroot yourDataroot --name yourTrainingModelSaveName \
--model YourModel  --input_nc 1 --output_nc 1 --preprocess None --batch_size 1 \
--gpu_ids 1 --phase test --direction AtoB --serial_batches \
--results_dir yourResultRoot \
--epoch 50 --num_test 1000
"""
Here input_nc and output_nc denote the input and output channel of generators
epoch choose a epoch to test
num_test max test number
"""
# Acknowledgments
Our code is inspired by [CycleGAN2017&Pix2Pix](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)\\
[PGAN-CGAN](https://github.com/icon-lab/pGAN-cGAN)
