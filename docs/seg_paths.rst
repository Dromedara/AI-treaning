.. _segmentationpaths:

Сегментация. Блоки, использующие фаловые пути
===================================================

Файл Segmentation.ipynb:
----------------------------


#6 ::

    class ArucoDataset(torch.utils.data.Dataset):
        def __init__(self, root, annFile, transforms):
            self.root = root

            with open('drive/MyDrive/VisionProject/Dataset/Labels.json') as f:

#10
::

    # use our dataset and defined transformations
    dataset = ArucoDataset('drive/MyDrive/VisionProject/Dataset/Data/', 'drive/MyDrive/VisionProject/Dataset/Labels.json', get_transform(train=True))
    dataset_test = ArucoDataset('drive/MyDrive/VisionProject/Dataset/Data/', 'drive/MyDrive/VisionProject/Dataset/Labels.json', get_transform(train=False)

#16
::

    torch.save(model.state_dict(), '/content/drive/MyDrive/VisionProject/Model/segmentation_model.pt')
    model.eval();

#19
::

    glob.glob('drive/MyDrive/VisionProject/Dataset/Data/')[0]

#20
::

    other_images = set(glob.glob('drive/MyDrive/VisionProject/Dataset/Data/'))
    other_images.difference_update(list(map(lambda x: 'drive/MyDrive/VisionProject/Dataset/Data/' + x, dataset.dataset.id2file.values())))
    other_images.difference_update(list(map(lambda x: 'drive/MyDrive/VisionProject/Dataset/Data/' + x, dataset_test.dataset.id2file.values())))
    other_images = list(other_images)

#27
::

    def view_examples(images, coco_annotations, images_dir='drive/MyDrive/VisionProject/Dataset/Data/', n=3):
        indices = np.random.choice([i for i in range(len(images))], n)
        images = np.array(images)
        coco_annotations = np.array(coco_annotations)

#30
::

    get_frames('/content/drive/MyDrive/VisionProject/Videos/video_1.mp4', './video/')

#37
::

    with open('drive/MyDrive/VisionProject/Dataset/Labels.json', 'r') as fw:
        labels = json.load(fw)
        labels['images'].extend(images)
        labels['annotations'].extend(coco_annotation)
        with open('drive/MyDrive/VisionProject/NewDataset/NewLabels.json', 'w') as fw:
            json.dump(labels, fw)

#39
::

    !cp /content/video/* /content/drive/MyDrive/VisionProject/NewDataset/Data/

#40
::

    !zip -r segmented_dataser.zip ./video/*
    !mv segmented_dataser.zip ./drive/MyDrive/VisionProject/NewDataset/
