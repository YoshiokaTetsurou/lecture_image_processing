# �ۑ�P���|�[�g

image�t�H���_���́utomica.png�v�����摜�Ƃ���D���̉摜�͏c512�摜�C��512��f�ɂ�鐳���`�̃f�B�W�^���J���[�摜�ł���D
```matlab:kadai1.m
ORG=imread('image\tomica.png'); % ���摜�̓���  
imagesc(ORG); axis image; % �摜�̕\��
```

�ɂ���āC���摜��ǂݍ��݁C�\���������ʂ�}�P�Ɏ����D

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_1.bmp)  
�}1 ���摜

���摜��1/2�T���v�����O����ɂ́C�摜��1/2�{�ɏk��������C2�{�Ɋg�傷��΂悢�D�Ȃ��C�g�傷��ۂɂ́C�P����Ԃ��邽�߂Ɂubox�v�I�v�V������ݒ肷��D

```matlab:kadai1.m
IMG = imresize(ORG,0.5); % �摜�̏k��  
IMG2 = imresize(IMG,2,'box'); % �摜�̊g��
```

1/2�T���v�����O�̌��ʂ�}�Q�Ɏ����D

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_2.bmp)  
�}2 1/2�T���v�����O

���l�Ɍ��摜��1/4�T���v�����O����ɂ́C�摜��1/2�{�ɏk��������C2�{�Ɋg�傷��΂悢�D���Ȃ킿�C

```matlab:kadai1.m
IMG = imresize(ORG,0.5); % �摜�̏k��  
IMG2 = imresize(IMG,2,'box'); % �摜�̊g��
```

�Ƃ���D1/4�T���v�����O�̌��ʂ�}�R�Ɏ����D

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_3.bmp)  
�}3 1/4�T���v�����O

1/8����1/32�T���v�����O�́C

```matlab:kadai1.m
IMG = imresize(ORG,0.5); % �摜�̏k��  
IMG2 = imresize(IMG,2,'box'); % �摜�̊g��
```

���J��Ԃ��D�T���v�����O�̌��ʂ�}�S�`�U�Ɏ����D

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_4.bmp)  
�}4 1/8�T���v�����O

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_5.bmp)  
�}5 1/16�T���v�����O

![���摜](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai1_6.bmp)  
�}6 1/32�T���v�����O

���̂悤�ɃT���v�����O�����傫���Ȃ�ƁC���U�C�N��̃T���v�����O�c�݂���������D
