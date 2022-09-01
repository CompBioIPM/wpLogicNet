# wpLogicNet

library(wpLogicNet)
################################################################################
# wpLogicNet: both logic gate and structure inference 
expression_data<- data_normalization(data$SOS1)
res            <- wpLogicNet(data = expression_data, density = "laplace", scale = 0.00071, number_of_em_iterations = 15, BF_threshold = 11)


expression_data<- data_normalization(data$SOS2)
res            <- wpLogicNet(data = expression_data, density = "laplace", scale = 0.00011, number_of_em_iterations = 15, BF_threshold = 4)


expression_data<- data$Y2
res            <- wpLogicNet(data = expression_data, density = "laplace", scale = 0.00021, number_of_em_iterations = 15, BF_threshold = 4)


expression_data<- data$Y3
res            <- wpLogicNet(data = expression_data, density = "logis", scale = 0.0002,  number_of_em_iterations = 10, BF_threshold = 3)


################################################################################
#  wpLogicNet_structure_aware: logic gate inference in structure-aware mode
expression_data<- data_normalization(data$SOS1)
res            <- wpLogicNet_structure_aware(data = expression_data, density = "norm", scale = 10^-3, true_edges = true_edges$SOS1, number_of_em_iterations = 10) 
predicted_gates<- res$predicted_gates              
a_posteriori_distributed_sample<- res$a_posteriori_distributed_sample
################################################################################
