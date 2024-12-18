## Note 👋
C#:
  1. Assign function for enum: https://stackoverflow.com/questions/49590253/be-able-to-call-a-function-from-an-enum-c-sharp
  2. Class from (string)ClassName: https://stackoverflow.com/questions/1044455/c-sharp-reflection-how-to-get-class-reference-from-string
  3. String to enum: https://stackoverflow.com/questions/16100/convert-a-string-to-an-enum-in-c-sharp

Python:
  1. https://stackoverflow.com/questions/3061/calling-a-function-of-a-module-by-using-its-name-a-string
  2. https://github.com/Belval/pdf2image

Git:
  1. https://github.com/github/gitignore/tree/main
     
AI:
  1. https://www.kaggle.com/code/debanga/faster-rcnn-a-gentle-introduction/notebook
  2. https://www.kaggle.com/code/pestipeti/pytorch-starter-fasterrcnn-train/notebook
  3. https://www.kaggle.com/code/debanga/faster-rcnn-a-gentle-introduction/notebook
  4. https://www.kaggle.com/code/benmanor/crater-object-detection-using-faster-rcnn/notebook
  5. https://colab.research.google.com/drive/1-I1j0c5TbA8l2L2FTjl0GFUeRswDzwPN?usp=sharing
  6. https://www.kaggle.com/code/kishor1210/train-faster-rcnn-using-keras/comments
  7. https://drive.google.com/drive/folders/13TkL0ju-jQg09OvRk_kUVavxIMNIu5AM?usp=sharing
  8. https://colab.research.google.com/drive/1Ic38gCj7tFcj46NbJGFpZc__sG_0sGES?usp=sharing
  9. https://pseudo-lab.github.io/Tutorial-Book-en/chapters/en/object-detection/Ch5-Faster-R-CNN.html
  10. https://stackoverflow.com/questions/71754254/text-line-segmentation-using-opencv-python
  11. https://stackoverflow.com/questions/9480013/image-processing-to-improve-tesseract-ocr-accuracy
  12. https://stackoverflow.com/questions/71462468/altering-pytorch-resnet-head-from-sigmoid-to-softmax
  13. https://www.kaggle.com/code/hrishikeshjadhav/multiclass-classification-using-resnet50
  14. https://github.com/ZhengJun-AI/MoirePhotoRestoration-MCNN?tab=readme-ov-file
  15. https://www.kaggle.com/code/boascent/multi-label-image-classification-pytorch-gpu
  16. https://www.scalablepath.com/machine-learning/chatgpt-architecture-explained
  17. https://github.com/cong-yang/MoireDet/tree/main/MoireDet
  18. https://pyimagesearch.com/2015/09/07/blur-detection-with-opencv/

  19. https://github.com/roboflow/tensorflow-object-detection-faster-rcnn/blob/master/tensorflow_object_detection_training_colab.ipynb

  20. Reload_to_retrain_torch: https://discuss.pytorch.org/t/loading-a-saved-model-for-continue-training/17244

  21. Preprocessing:
        - https://github.com/wkentaro/labelme
        - https://github.com/aleju/imgaug
        - https://albumentations.ai/
        - https://stackoverflow.com/questions/67330319/how-to-improve-image-alignment-with-opencv
     
        - https://pytorch.org/vision/main/models/generated/torchvision.models.detection.maskrcnn_resnet50_fpn.html
        - https://pytorch.org/vision/main/auto_examples/others/plot_visualization_utils.html#instance-seg-output
          
  22. Voice Cloning
  23. Text-to-speech
  24. Text-to-Video
  25. https://www.quora.com/Is-it-possible-to-use-both-CPUs-and-GPUs-for-training-deep-learning-models-If-yes-how-can-one-do-that-in-PyTorch#:~:text=Yes%2C%20it%20is%20possible%20to,nn.
  26. https://github.com/iCGY96/awesome_OpenSetRecognition_list?tab=readme-ov-file
      
Scripts:
  1. https://github.com/massgravel/microsoft-activation-scripts
  2. https://stackoverflow.com/questions/515309/what-does-cmd-c-mean
  3. https://www.manageengine.com/products/desktop-central/script-templates/latest-script.html
     
FrontEnd:
  1. https://freefrontend.com/
     
QR:
  1. https://pypi.org/project/qreader/

Windows:
  1. https://learn.microsoft.com/en-us/answers/questions/354631/using-wmi-uninstall-commands-with-variables
  2. Uninstall application:
      # Uninstall Script for Specific Software
      
      This script helps uninstall a specific software by searching for its uninstall string in both 32-bit and 64-bit registry paths.
      
      ## Script
      
      ```powershell
      $uninstall32 = gci "HKLM:\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall" | foreach { gp $_.PSPath } | ? { $_ -match "SOFTWARE NAME" } | select UninstallString
      $uninstall64 = gci "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall" | foreach { gp $_.PSPath } | ? { $_ -match "SOFTWARE NAME" } | select UninstallString
      
      if ($uninstall64) {
          $uninstall64 = $uninstall64.UninstallString -Replace "msiexec.exe","" -Replace "/I","" -Replace "/X",""
          $uninstall64 = $uninstall64.Trim()
          Write "Uninstalling..."
          start-process "msiexec.exe" -arg "/X $uninstall64 /qb" -Wait
      }
      
      if ($uninstall32) {
          $uninstall32 = $uninstall32.UninstallString -Replace "msiexec.exe","" -Replace "/I","" -Replace "/X",""
          $uninstall32 = $uninstall32.Trim()
          Write "Uninstalling..."
          start-process "msiexec.exe" -arg "/X $uninstall32 /qb" -Wait
      }
  3. "this operation has been cancelled due to restrictions in effect on this computer":
     
       Windows + R -> HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer -> Delete "NoViewOnDrive"
  4. https://learn.microsoft.com/en-us/dotnet/framework/windows-services/how-to-install-and-uninstall-services
  5. Using Automation to interact with some app
       - https://gist.github.com/DBremen/0e73989fbe49a538331a8c36b9f905ae
       - Get Elements:
         
           ```powershell
             Add-Type -AssemblyName UIAutomationClient
              Add-Type -AssemblyName UIAutomationTypes
              $calc = [Diagnostics.Process]::Start('calc')
              # waiting process start
              $null = $calc.WaitForInputIdle(5000)
              sleep -s 2
              
              # get main windows title id
              $calcWindowId = ((Get-Process).where{$_.MainWindowTitle -eq 'Calculator'})[0].Id
              $root = [Windows.Automation.AutomationElement]::RootElement
              $condition = New-Object Windows.Automation.PropertyCondition([Windows.Automation.AutomationElement]::ProcessIdProperty, $calcWindowId)
              $calcUI = $root.FindFirst([Windows.Automation.TreeScope]::Children, $condition)
              
              # find all button
              $buttonCondition = New-Object Windows.Automation.PropertyCondition([Windows.Automation.AutomationElement]::ClassNameProperty, "Button")
              $buttons = $calcUI.FindAll([Windows.Automation.TreeScope]::Descendants, $buttonCondition)
              
              # print buttons name
              $buttons | ForEach-Object {
                  $_.Current.Name
              }


