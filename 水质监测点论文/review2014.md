### Abstract   
Several methodologies have been suggested in the past two decades by different researchers to locate sensors in water distribution networks with different objectives. 
Even though a large number of methodologies have been developed, there is no consensus amongst researchers on the objectives, methodology and other aspects of sensor placements. 
The methodologies on sensor placement have been broadly classified into two categories as single objective and multi objective sensor location problems and compared on different basis. 
A critical review of available methodologies is presented to suggest future research needs for sensor network design for real life networks.
在过去的二十年中，不同的研究人员已经提出了几种方法，用于在具有不同目标的配水网络中定位传感器。 
尽管已经开发了大量方法，但研究人员对传感器放置的目标，方法和其他方面尚未达成共识。 
传感器放置的方法大致分为单目标和多目标传感器位置问题两类，并在不同的基础上进行比较。 
对可用方法进行了严格审查，以提出对现实生活网络传感器网络设计的未来研究需求。

### Introduction   
The main objective of a water distribution network (WDN) is to provide safe water to the consumers in adequate quantity. 
Water quality may deteriorate substantially during transport from the treatment plant to the consumer. 
Therefore, water quality at various locations in a public water supply network is routinely monitored.
After terrorist attack, more emphasis is being provided to online monitoring of water quality using sensors and several new objectives for location of sensors/monitoring points are being considered.   
配水网络(WDN)的主要目标是为消费者提供足够数量的安全饮用水。 
在从处理厂运输到消费者的过程中，水质可能会显着恶化。 
因此，常规监测公共供水网络中各个位置的水质。 
在恐怖袭击之后，正在更加重视利用传感器对水质进行在线监测，并正在考虑若干新的传感器/监测点定位目标。

The new objectives are related to: 
(i) early detection of any contamination event, such as time to detection (TD);
(ii) minimizing the impact or consequences of contamination event, such as volume of water consumed (VC),population exposed to contamination (PE), and extent of contamination (EC). 
Theoretically, contaminant may enter at any point in WDN and at any time, which obviously require monitoring at each node and is practically not feasible. 
Therefore, attempts have also been made to cover maximum population with limited number of sensors considering (i) associated risk (Risk) and/or (ii) maximizing detection likelihood (DL) of contamination events. 
A sensor may detect a contamination event falsely or may not detect a contamination event if the contamination concentration is below certain detectable limits. 
Further, there may be delay in response from sensors deployed. 
Therefore, additional objectives as minimization of sensor response time (SRT), minimization of number of failed detection (NFD)/minimization of probability of failed detection (PFD) and sensor detection redundancy (SDR) have also been considered.
Time delay is used to differentiate two systems of MSs having same DL but different TD.   
新目标涉及：
(i)及早发现任何污染事件，例如检测时间(TD);
(ii)尽量减少污染事件的影响或后果，例如消耗的水量(VC)，暴露的人口污染(PE)和污染程度(EC)。
从理论上讲，污染物可能随时进入WDN的任何一点，这显然需要在每个节点进行监测，实际上是不可行的。
因此，还考虑(i)相关风险(风险)和/或(ii)最大化污染事件的检测可能性(DL)，尝试覆盖具有有限数量传感器的最大人口。
如果污染物浓度低于某些可检测限度，则传感器可能错误地检测污染事件或者可能检测不到污染事件。
此外，部署的传感器的响应可能会延迟。
因此，还考虑了诸如最小化传感器响应时间(SRT)，最小化失败检测次数(NFD)/最小化检测失败概率(PFD)和传感器检测冗余(SDR)的附加目标。
时间延迟用于区分具有相同DL但不同TD的两个MS系统。 MS:监测传感器
TD:检测时间
VC:消耗水量
PE:暴露的人口污染
EC:污染程度

The main objective of this paper is to review the methodologies related to locations of monitoring points or sensors in WDNs. 
Several methodologies have been developed to tackle the problem of sensor placements with single or multiple objectives. 
Hart and Murray [1] comprehensively reviewed available literature till 2008-09 on sensor placement strategies and identified key issues that need to be addressed in future work. 
A lot of research work has been reported after that. A comprehensive review until date is provided in this paper along with critiques. 
Further, some of the issues that are required to be considered in future work are presented.
本文的主要目的是审查与WDN中监测点或传感器位置相关的方法。 
已经开发了几种方法来解决具有单个或多个目标的传感器放置问题。 
Hart和Murray [1]全面审查了截至2008 - 09年的有关传感器放置策略的现有文献，并确定了未来工作中需要解决的关键问题。 
之后报道了很多研究工作。 本文提供了一个全面的评论以及批评。 
此外，还介绍了未来工作中需要考虑的一些问题。

### 2. Single and Multi-objective Sensor Location Problems   
Based on number of performance objectives, research work on location of sensors/monitoring stations is classified herewith as single objective or multi-objective problems. Performance objectives are those which provide performance characteristics of monitoring system. General parameters considered for comparison of different methodologies are: (i) need of hydraulic and water quality simulation; (ii) methodology used for solving problem; (iii) Network(s) considered for illustration; and (iv) fixed/ variable number of sensors. All the works based on any single objective are presented in Table 1 [2-22].
基于性能目标的数量，传感器/监测站的位置研究工作在此归类为单目标或多目标问题。 性能目标是提供监视系统性能特征的目标。 考虑用于比较不同方法的一般参数是：(i)需要水力和水质模拟; (ii)用于解决问题的方法; (iii)考虑用于说明的网络; (iv)固定/可变数量的传感器。 基于任何单一目标的所有工作见表1 [2-22]。

#### 2.1. Single Objective problems
Safe quality of water at monitoring node assures delivery of safe water at all upstream nodes through which major portion of supply (termed as coverage criteria) received at monitoring node has passed. 
The DC of MS is defined as total demand of all those nodes, which can be assumed to be safe if quality of water at monitoring node is safe [2]. Lee and Deninger [2], Alzahrani et al. [5], and Afshar and Marino [9] used MIP, GA and ACO respectively to locate given number of MSs to maximize the DC based on selected coverage criteria.
Woo [4] emphasized use of water quality simulation to develop coverage matrix. 
Kumar et al. [3] and Kansal et al. [7] proposed more systematic way of preparing coverage matrix and suggested heuristic method to locate MSs one by one, by selecting best location first and modifying coverage matrix by eliminating nodes already covered to select next station. 
Ghimire et al. [6], and Rathi and Gupta [8] also suggested heuristic methods to simplify the problem. Method based on DC gives importance to coverage and therefore tries to locate MS as far away as possible from source based on coverage criteria. They aregood for location of MS required for regular monitoring against accidental contamination. 
监测节点处的水的安全质量确保在所有上游节点处输送安全水，通过该节点，在监测节点处接收的主要供应部分(称为覆盖标准)已经过去。 MS的DC定义为所有节点的总需求，如果监测节点的水质安全，可以认为是安全的[2]。 
Lee和Deninger [2]，Alzahrani等[5]，Afshar和Marino [9]分别使用MIP，GA和ACO来定位给定数量的MS，以根据选定的覆盖标准最大化DC。 
Woo[4]强调使用水质模拟来开发覆盖矩阵。
库马尔等人[3]和Kansal等人[7]提出了更系统的准备覆盖矩阵的方法，并提出了一种逐一定位MS的启发式方法，首先选择最佳位置，通过消除已经覆盖的节点来修改覆盖矩阵，以选择下一站。 
Ghimire等[6]，Rathi和Gupta[8]也提出了启发式方法来简化问题。基于DC的方法重视覆盖，因此尝试基于覆盖标准尽可能远离源定位MS。它们适用于定期监测意外污染所需的MS位置。

Anearly detection of contamination event is desirable. 
Kumar et al. [10] suggested TD, defined as the time elapsed between the entry of contaminant and its detection by any of the MS and used it as a measure for level of service (LOS) to consumers. They identified best monitoring locations one by one by constructing and using traveltime matrix for desired LOS.
Chastain et al. [12] developed a heuristic methodology considering extended period water quality analysis for creating database of water system responses by injecting contaminant at each node. The method searched the best locations of MS one by one to maximize the covered nodes with the condition of time to detect. 
Rathi and Gupta [13] also suggested a heuristic method, which works on appended shortest travel time tree to identify best locations of MSs to achieve desired T-hr LOS. The number of MSs increases as the desired LOS increases. With constraints on number of sensors, the desired LOS may not be achieved. Most of the multi objective sensor location methodologies considered TD as one of the objective.
需要无差别地检测污染事件。
库马尔等人[10]建议TD，定义为污染物进入与任何MS检测之间经过的时间，并将其用作衡量消费者服务水平(LOS)的指标。他们通过构建和使用所需LOS的旅行时矩阵逐个确定最佳监测位置.
Chastain等[12]开发了一种启发式方法，考虑延长期水质分析，通过在每个节点注入污染物来创建水系统响应数据库。该方法一个接一个地搜索MS的最佳位置，以便在检测时间的条件下最大化覆盖节点。
Rathi和Gupta[13]也提出了一种启发式方法，该方法适用于附加的最短旅行时间树，以识别MS的最佳位置，以实现所需的T-hr LOS。随着期望的LOS增加，MS的数量增加。由于传感器数量的限制，可能无法实现所需的LOS。大多数多目标传感器定位方法都将TD视为目标之一。

Kessler et al. [15] suggested total volume of contaminated water consumed (VC) before detection of any event to quantify the impact of contamination event. The LOS is decided by pre-specified value of VC. They developed pollution matrix for a given level of service and identified an appropriate set of MSs, which covered all events. 
Ostfeld and Salomons [16] considered random multiple contamination events to decide location of MSs. Random pollution matrix was generated by considering LOS in terms of VC and GA was used to identify location of MSs. 
Ostfeld and Salomons [17,18] extended the methodology to consider randomness of flow rate of injected pollutant, randomness in consumers’ demands, and the detection sensitivity and response time of MSs.
凯斯勒等人[15]建议在检测到任何事件之前消耗的污染水总量(VC)，以量化污染事件的影响。 LOS由预先指定的VC值决定。 他们针对特定服务水平开发了污染矩阵，并确定了一组适当的MS，涵盖了所有事件。 
Ostfeld和Salomons[16]考虑随机多重污染事件来决定MS的位置。 通过考虑LOS的VC生成随机污染矩阵，GA用于识别MS的位置。 
Ostfeld和Salomons[17,18]扩展了该方法，考虑了注入污染物流速的随机性，消费者需求的随机性，以及MS的检测灵敏度和响应时间。

Berry et al. [19] considered LOS in terms of expected fraction of population at risk and identified optimal sensors locations using MIP. 
Berry et al. [23] and Propato et al. [24] formulated MIP model in such a way that wide range of design objectives can be accommodated in the formulation, either individually or jointly. 
Berry et al. [23] quantified the impact of each contamination event by multiplying: (1) The probability of events, (2) A binary (1, 0) contamination indicator and (3) impact value evaluated from dynamic water quality simulation. 
Propato et al.[24] considered minimization of impact associated with contamination scenario in terms of TD, PE, VC, contaminated mass consumed (CMC), and probability/percentage of failed detection (PFD). Since projected nodal demand has inherent uncertainty, several researchers incorporated it in deciding sensor locations with objective of minimizing expected population exposed [20,21] or detection time [14]. 
Berry等人[19]根据风险人口的预期分数考虑了LOS，并使用MIP确定了最佳传感器位置。 
Berry等人[23]和Propato等人[24]制定MIP模型，使得配方中的各种设计目标可以单独或共同适应。 
Berry等人[23]通过乘以以下来量化每个污染事件的影响：(1)事件概率，(2)二元(1,0)污染指标和(3)动态水质模拟评估的影响值。 
Propato等人[24]考虑在TD，PE，VC，污染物质消耗(CMC)和失败检测概率/百分比(PFD)方面最小化与污染情景相关的影响。 由于预计的节点需求具有固有的不确定性，一些研究人员将其纳入决定传感器位置，目标是尽量减少预期人口暴露[20,21]或检测时间[14]。

Each objective has its own advantage and provides different set of locations. 
Watson et al. [25] demonstrated that sensor placement using one objective provides greater risk. They observed that majority of objectives are uncorrelated, and an optimal solutions associated with one objective function could be highly sub-optimal with respect to another design objective. 
Murray et al. [26] compared sensor placement solution considering three objectives PE, EC, DL using 8 example networks of varying size for illustrations and showed that number of sensors needed for various objectives depends upon marginal benefit achieved or acceptable risk defined by water utilities.
每个目标都有自己的优势，并提供不同的位置。 
Watson等人[25]证明使用一个物镜的传感器放置提供了更大的风险。 他们观察到大多数目标是不相关的，并且与一个目标函数相关的最优解决方案相对于另一个设计目标可能是高度次优的。 
默里等人[26]比较了传感器放置解决方案，考虑了三个目标PE，EC，DL，使用8个不同大小的示例网络进行说明，并表明各种目标所需的传感器数量取决于实现的边际效益或水务公司定义的可接受风险。

Bahadur et al. [27] assessed the impact of both spatial and temporal population variability on sensor network design and observed it to be significant. Since limited sensors are to be used, this makes sensor location crucial. Therefore, in order to provide a balance solution using limited number of sensors researchers suggested different algorithms based on multiple objectives.
Bahadur等[27]评估了空间和时间人口变异对传感器网络设计的影响，并认为它具有重要意义。 由于要使用有限的传感器，这使得传感器位置至关重要。 因此，为了使用有限数量的传感器提供平衡解决方案，研究人员提出了基于多个目标的不同算法。

#### 2.2. Multi-objective problems   
Various researchers had used two types of multi objective approaches. Some researchers considered the approaches in which the objective functions remain mutually distinct and result is expressed in the form of Pareto front ([24],[28-36]) and other approaches in which the different objectives considered are grouped together in a single objective function which is then solved using optimization solver[37-42]. The available multi-objective
methodologies are given in Table 2 in the chronological order of their development.
各种研究人员使用了两种类型的多目标方法。 一些研究人员考虑了目标函数保持相互不同的方法，结果以帕累托前沿([24]，[28-36])和其他方法表达，其中考虑的不同目标在一个目标中组合在一起 然后使用优化求解器[37-42]求解函数。 
表2按其发展的时间顺序给出了可用的多目标方法。

It can be observed from Table 2 that few additional objectives such as contamination source detection likelihood (CSDL) as used by [31], Risk as used by [33], Detection Likelihood (DL) and Response delay of Sensors as used by [17,18], Sensor Detection Redundancy (SDR) as used by [31,32]etc. are suggested as performance indicator of monitoring system. 
Since limited number of sensors is provided for monitoring, there is possibility that some of the contamination events are not detected by any of the sensor. Therefore, detection likelihood, defined as probability of contamination events being detected by any sensor, or probability of failed detection, defined as probability of contamination events not being detected by any of the sensor are considered.
从表2中可以看出，[13]使用的污染源检测可能性(CSDL)，[33]使用的风险，检测可能性(DL)和传感器的响应延迟[17]使用的其他目标很少。 ，[18]，[31,32]等使用的传感器检测冗余(SDR)。 建议作为监测系统的性能指标。 
由于提供了有限数量的传感器用于监测，因此任何传感器都可能检测不到某些污染事件。 因此，检测可能性，定义为由任何传感器检测到的污染事件的概率，或检测失败的概率，被定义为任何传感器未检测到污染事件的概率。

Further, it may be possible that contamination events are detected by multiple sensors, and therefore term sensor detection redundancy defined as probability of detection of contamination event by specified number of sensors within specified time. The response delay by sensor is measured by time elapsed between registration of contamination event at sensor and response provided by it [17, 18];[48]). 
Bristow et al. [49] model the response time in various phases and defined it as the time between initial detection of a contamination event and individual user stops using contaminated water.
此外，有可能由多个传感器检测污染事件，并且因此术语传感器检测冗余被定义为在指定时间内通过指定数量的传感器检测污染事件的概率。 传感器的响应延迟是通过传感器上的污染事件登记和由它提供的响应之间经过的时间来测量的[17,18]; [48]。 
Bristow等人[49]模拟不同阶段的响应时间，并将其定义为初始检测到污染事件和个人用户停止使用污染水之间的时间。

As mentioned earlier TD is the most preferred objective in multi-objective problems as it forces early detection of contamination events. It is coupled with one or more complementary objectives that quantify impact of contamination event with one or more competing objectives such as detection likelihood or coverage. Ostfeld et al. [50] compared solution provided by several algorithms based on four objectives: (1) TD; (2) PE; (3) VC; and (4) DL. The solutions provided by different algorithms were quite varied.
如前所述，TD是多目标问题中最优选的目标，因为它强制早期检测污染事件。 它与一个或多个互补目标相结合，可以量化污染事件对一个或多个竞争目标(如检测可能性或覆盖范围)的影响。 
Ostfeld等[50]比较了基于四个目标的几种算法提供的解决方案：(1)TD; (2)PE; (3)VC; (4)DL。 不同算法提供的解决方案各不相同。

Even though various research groups have demonstrated the ability to solve large-scale problems, this is not a robust capability that can be applied by potential end users. This raises important questions about the reliability of such designs, and it highlights the need of memory-limited optimizers. GA is the most preferred solver for multiobjective optimization problem. The computational requirement in GA increases with the size of network and number of contamination scenario required to be considered, which poses restriction on its application to large 
network problems. Heuristic algorithms have their own limitations. Another problem observed especially in developing country that no well-calibrated model for the network is available which is considered to be the most important requirement of most of methodologies. Therefore, recently researchers have developed the methodologies for real world problem to tackle the complexity of the network and reduce the computer runtime [54-58]. 
尽管各种研究小组已经证明了解决大规模问题的能力，但这并不是潜在最终用户可以应用的强大功能。 这引发了关于此类设计可靠性的重要问题，并强调了内存限制优化器的需求。 GA是多目标优化问题的首选求解器。 GA中的计算要求随着网络的大小和需要考虑的污染场景的数量而增加，这对其应用程序的大量限制网络问题。 启发式算法有其自身的局限性。 特别是在发展中国家观察到的另一个问题是，没有经过良好校准的网络模型，这被认为是大多数方法学中最重要的要求。 因此，最近研究人员开发了现实世界问题的方法，以解决网络的复杂性并减少计算机运行时间[54-58]。

It can be observed from the reported literature that there is no consensus amongst researchers on number and type of performance objectives to be considered and several other issues related to sensor location problem. Considering the applicability of algorithms developed in future to real life networks some issues are raised in next section, which may be helpful in developing some consensus amongst researchers.
从报告的文献中可以看出，研究人员没有就要考虑的性能指标的数量和类型以及与传感器位置问题相关的其他几个问题达成共识。 考虑到将来开发的算法适用于现实生活网络，下一节将提出一些问题，这可能有助于在研究人员之间达成一些共识。

### 3. Issues need consensus for future research
Original or Reduced Network: A real life network may involve thousands of pipe and nodes, and numbers of sensors are restricted. Considering each and every node of original network as possible location of sensor may unnecessarily increase computational burden, which can be significantly reduced by suitably eliminating some of the nodes from list of candidate nodes such that sensor placement accuracy is not affected.
原始网络或简化网络：现实生活中的网络可能涉及数千个管道和节点，并且传感器的数量受到限制。 将原始网络的每个节点视为传感器的可能位置可能不必要地增加计算负担，这可以通过从候选节点列表中适当地消除一些节点而显着减少，使得传感器放置精度不受影响。

Number of loadings: Water demand changes throughout the day so as the water level changes in the reservoir throughout the day, and therefore practically flow scenario in network changesin every moment. This requires consideration of dynamic analysis at suitable interval. The computational requirement can be substantially reduced by identifying few important scenarios with respect to nodal demands, pumps on and off situation and flows in and out conditions from tanks.
负荷数量：全天需水量变化，以便水库全天水位发生变化，因此每时每刻都会出现网络变化的实际情况。 这需要以适当的间隔考虑动态分析。 通过识别关于节点需求，泵打开和关闭情况以及来自罐的流入和流出条件的几个重要场景，可以显着减少计算要求。

Number of contamination events and their locations: A contaminant may enter in network from any point and at any time. Further, there could be more than one location of contaminant intrusion at any time. Instead of considering every node as possible location of entry of contaminant, few vulnerable locations can be selected to reduce the computational work.
污染事件的数量及其位置：污染物可能随时随地进入网络。 此外，任何时候都可能存在多个污染物侵入位置。 不是将每个节点都视为污染物进入的可能位置，而是可以选择很少的易受攻击的位置来减少计算工作。

Number of performance objectives: One objective is certainly not enough and multiple objectives are necessary to obtain a balanced solution. Selection of too many objectives at a time increases the computational requirement. Selection of objectives should be such that a balanced design could be obtained with respect to different objectives. Some complementary type of objectives can be dropped.
绩效目标的数量：一个目标肯定是不够的，需要多个目标才能获得平衡的解决方案。 一次选择太多目标会增加计算要求。 目标的选择应使得可以针对不同的目标获得平衡的设计。 可以放弃一些互补的目标。

Type of solution methodology: Preferred solution methodology is one that can prioritize selection with respect to different objectives considered in the sensor location problems. Prioritize selection helps in future extension of monitoring locations.
解决方案类型的方法：首选解决方案方法是可以根据传感器位置问题中考虑的不同目标确定选择的优先级。 优先选择有助于将来扩展监控位置。

### 4. Summary and conclusions
The issue of water system security after the terrorist attack in 2001 has motivated several researchers to develop a methodology for sensor location to prevent public from impact of deliberate contaminations. Several performance objectives for evaluating monitoring system have been considered. In spite of lot of research there is no consensus amongst researchers on several issues related to sensor location problems. A critical review of available methodologies is presented in this paper with a view to raise issues requiring consensus amongst researchers. The 
research work pertaining to these issues are highlighted for developing consensus amongst researchers for future research work on sensor location problems. 
2001年恐怖袭击事件后的水系统安全问题促使一些研究人员开发出一种传感器定位方法，以防止公众受到蓄意污染的影响。 已经考虑了评估监测系统的若干性能目标。 尽管进行了大量研究，但研究人员尚未就与传感器位置问题相关的几个问题达成共识。 本文介绍了对可用方法的严格审查，以期提出需要研究人员达成共识的问题。该有关这些问题的研究工作得到强调，以便在研究人员之间就传感器位置问题的未来研究工作达成共识。

中科院JCR期刊分区
CUGWH  5043