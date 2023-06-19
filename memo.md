# 研究ノート
## 先行研究のコードを動かす
#### 必要なtopic(bagFile.bagを参考)
```
path:        bagFile.bag
version:     2.0
duration:    2:35s (155s)
start:       Nov 23 2016 14:10:42.41 (1479877842.41)
end:         Nov 23 2016 14:13:17.69 (1479877997.69)
size:        392.8 MB
messages:    99733
compression: none [108/108 chunks]
types:       diagnostic_msgs/DiagnosticArray         [60810da900de1dd6ddd437c3503511da]
             dynamic_reconfigure/Config              [958f16a05573709014982821e6822580]
             dynamic_reconfigure/ConfigDescription   [757ce9d44ba8ddd801bb30bc456f946f]
             geometry_msgs/PoseWithCovarianceStamped [953b798c0f514ff060a53a3498ce6246]
             nav_msgs/MapMetaData                    [10cfc8a2818024d3248802c00c95f11b]
             nav_msgs/OccupancyGrid                  [3381f2d731d4076ec5c71b0759edbe4e]
             nav_msgs/Odometry                       [cd5e73d190d741a2f92e81eda573aca7]
             rosgraph_msgs/Log                       [acffd30cd6b6de30f120938c17c593fb]
             sensor_msgs/JointState                  [3066dcd76a6cfaef579bd0f34173e9fd]
             sensor_msgs/LaserScan                   [90c7ef2dc6895d81024acba2ac42f369]
             std_msgs/Float64                        [fdb28210bfa9d7c91146260178d9a584]
             tf2_msgs/TFMessage                      [94810edda583a504dfda3829e70d7eec]
topics:      /combine_dr_measurements/odom_combined    3881 msgs    : geometry_msgs/PoseWithCovarianceStamped
             /diag_scan                                6228 msgs    : sensor_msgs/LaserScan                  
             /diagnostics                               465 msgs    : diagnostic_msgs/DiagnosticArray         (3 connections)
             /hokuyo_node/parameter_descriptions          1 msg     : dynamic_reconfigure/ConfigDescription  
             /hokuyo_node/parameter_updates               1 msg     : dynamic_reconfigure/Config             
             /hokuyo_node_0/parameter_descriptions        1 msg     : dynamic_reconfigure/ConfigDescription  
             /hokuyo_node_0/parameter_updates             1 msg     : dynamic_reconfigure/Config             
             /icart_mini/odom                         15515 msgs    : nav_msgs/Odometry                      
             /joint_states                            15508 msgs    : sensor_msgs/JointState                 
             /map                                        21 msgs    : nav_msgs/OccupancyGrid                 
             /map_metadata                               21 msgs    : nav_msgs/MapMetaData                   
             /rosout                                  15541 msgs    : rosgraph_msgs/Log                       (11 connections)
             /rosout_agg                              15521 msgs    : rosgraph_msgs/Log                      
             /scan                                     6230 msgs    : sensor_msgs/LaserScan                  
             /slam_gmapping/entropy                      15 msgs    : std_msgs/Float64                       
             /tf                                      20783 msgs    : tf2_msgs/TFMessage                      (3 connections)
```
TFの中身→[farme.pdf](https://github.com/AtsukiUsui/study_of_intensity/blob/main/data/frames.pdf)

#### やること
* LiDARのマウント作成  
* rosbagを取る用のlaunchファイル起動  
  Cat：RPLidar,URG,モーター,コントローラを動かす  
  PC ：gmapping,rosbag recordを動かす
    * TFの中身に地面見る用LIDARがあるのでURDFを書き換える
    * ⇡きちんと適応されているか確認する
    * catでURGとrplidarどっちも使えるか確認する