# Investigating the real-time performance by computing Utilization using ROS [Click here to view the PDF](./robotics.pdf)

# Abstract
Recent advancements in autonomous vehicles such as delivery robots, maritime and commercial vehicles have resulted in renewed interest in the field of autonomous driving. One of the important aspects
involves quantizing how well the technologies involved in autonomous driving execute and research in
this field has been of vital importance. Simultaneous Localization and Mapping (SLAM) is an approach
that enables machines to create maps and understand their location in real-time. Visual SLAM represents
a distinct variant within the realm of SLAM systems, utilizing 3D vision to execute tasks of localization
and mapping even in situations where both the sensor’s location and the surrounding environment remain
unfamiliar The goal of this paper is to document the execution of OV2Slam Algorithm with a subset of
KITTI data and also benchmark the results with boxplots and calculations involved. We also have a look
at the utilization time of a chunk of KITTI data in OV2Slam
# 1 Introduction
Robotics, augmented reality, and autonomous vehicles have been at the forefront of technological evolution, significantly influenced by the capabilities of computational frameworks such as the Robot Operating
System (ROS). Visual SLAM (Simultaneous Localization and Mapping) technology stands as a pivotal
innovation in this domain, enabling camera-equipped devices to adeptly navigate unknown terrains while
concurrently constructing maps. A notable contribution to this field is OV2SLAM, an online VSLAM algorithm which stands out for its real-time capability, accuracy, and robustness. With its unique four-thread
architecture comprising the Front End, Mapping, State Optimization, and Loop Closer, OV2SLAM optimizes efficiency through multithreading, presenting state-of-the-art accuracy and real-time performance
when juxtaposed against its counterparts.
In light of the above, this paper embarks on an in-depth exploration of real-time performance by computing utilization using ROS in tandem with OV2SLAM. By incorporating the KITTI dataset, a benchmark
in the autonomous driving domain, our methodology discerns the utilization of various processes in relation
to the frame rate. This intersection of theoretical paradigms and practical applications aspires to provide developers and researchers with holistic insights. The rest of this paper first discusses related work in Section 2
which builds an understanding for evaluation metrics, and then describes our implementation in Section 4.
Section 5 describes how we evaluated our system and presents the results. Section 6 presents our conclusions
and describes future work.
# 2 Related Work
Several papers in the domain of robotic autonomy have proposed innovative methodologies to address
challenges related to energy management and SLAM performance.
Towards A Multi-Mission QoS and Energy Manager for Autonomous Mobile Robots [1] pointed out
several areas that, while notable, still had room for improvement when juxtaposed against our methods.
One key methodology, energy-aware path and motion planning, proposed in previous works like [2] and [3],
focuses on path optimization to conserve energy. However, they tend to overlook the constraints posed by
the robot’s limited computing resources. This oversight implies that despite following an energy-efficient
trajectory, the robot could still confront computational challenges due to resource limitations. Furthermore,
in [4], the emphasis on battery management compromises between the peril of battery exhaustion and the
achievement of mission objectives. While the redirection of robots to docking stations for recharging is
factored in, this method primarily pivots around energy management without adequately addressing limited
computational resources, crucial for ensuring a robot’s autonomy.
In another significant study, Towards a Framework for SLAM Performance Investigation on Mobile
Robots [5], a method to assess two SLAM algorithms, Google Cartographer and Hector SLAM, was proposed. Utilizing ROS as middleware and Nvidia Jetson TX2 as the computational platform, they evaluated the algorithms based on metrics like accuracy, processing time, and hardware resource consumption
(CPU and RAM usage). This analysis proved instrumental in our research. Their findings indicated Hector
SLAM’s superior accuracy compared to Cartographer, albeit at the cost of Cartographer’s exceptional time
performance, which demanded a higher CPU and RAM allocation
#3 Datasets used
The KITTI dataset [6], a cornerstone in computer vision research related to autonomous vehicles, encompasses a vast array of data. However, given the challenges posed by limited computational resources and
storage capacities often encountered in academic settings, it’s sometimes necessary to focus on smaller portions of this expansive dataset. In our study, we particularly concentrated on Dataset 0096. This subset
retains a comprehensive collection of the raw images typically found in KITTI, including data from both
left and right camera perspectives. While Dataset 0096 is more compact, it offers a representative sample
of the larger dataset, ensuring that our analyses and findings maintain validity and relevance. The ability to
work with such a subset empowers researchers to continue pushing the boundaries of knowledge without
being hamstrung by technological constraints.
In our research, to thoroughly analyze the values of all frames within the Dataset 0096 of the KITTI
data, we processed the dataset through OV2Slam. This allowed us to extract precise measurements for
each consecutive frame. Based on the extracted data, we then generated a boxplot to visually represent
the distribution and variance of values across frames. Additionally, we computed descriptive statistics,
identifying the minimum, maximum, and average values. This rigorous approach ensured a comprehensive
understanding of the dataset’s characteristics.
