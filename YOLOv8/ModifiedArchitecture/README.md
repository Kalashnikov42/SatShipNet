A modified architecture for YOLOv8 Algorithm exclusively for ship detection

# ARCHITECTURE 

model:
type: yolo
backbone:
   type: CSPDarknet53  # chosen backbone
   args:
     depth: 53
neck:
   type: BIFpNN  # new neck component
   args:
       in_channels_list: [256, 512, 1024]
       out_channels: 256
head:
    type: YOLOv8Head
    args:
      in_channels: [256, 256, 256]
      num_classes: 80  # number of classes
