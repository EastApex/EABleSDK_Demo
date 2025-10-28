# Uncomment the next line to define a global platform for your project
 platform :ios, '13.0'

target 'EASDKDemo' do
  # Comment the next line if you don't want to use dynamic frameworks
 use_frameworks!

  pod 'SnapKit'
  
  pod 'YYKit'
  pod 'EABleSDK', :git => 'https://github.com/EastApex/EABleSDK.git'



 # if Xcode version is 14.3 will open this

  post_install do |installer|
    installer.pods_project.targets.each do |target|
      target.build_configurations.each do |config|
        config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '13.0'
      end
    end
  end

 # else ignore 
  
end
