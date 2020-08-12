platform :ios, '9.0'

use_frameworks!
inhibit_all_warnings!

workspace "UIKitVoxel"

pod 'SwiftLint'

abstract_target 'VoxelTargets' do

    def shared_test_pods
        pod 'iOSSnapshotTestCase'
        pod 'KIF/IdentifierTests'
    end

    #########################################
    # UIKitVoxel (Framework)                #
    #########################################

    target 'UIKitVoxel' do
        project 'UIKitVoxel/UIKitVoxel.xcodeproj'
        
        target 'UIKitVoxelTests' do
            project 'UIKitVoxel/UIKitVoxel.xcodeproj'
            shared_test_pods
        end
    end
    
    #########################################
    # UIKitVoxelExample (App)               #
    #########################################

    target 'UIKitVoxelExample' do
        project 'UIKitVoxelExample/UIKitVoxelExample.xcodeproj'
    end

    #########################################
    # UIKitVoxelCommunity (Framework)       #
    #########################################

    target 'UIKitVoxelCommunity' do
        project 'UIKitVoxelCommunity/UIKitVoxelCommunity.xcodeproj'
        
        target 'UIKitVoxelCommunityTests' do
            project 'UIKitVoxelCommunity/UIKitVoxelCommunity.xcodeproj'
            shared_test_pods
        end
    end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['GCC_WARN_INHIBIT_ALL_WARNINGS'] = 'Yes'
            config.build_settings['CLANG_WARN_STRICT_PROTOTYPES'] = 'Yes'
        end
    end
end
