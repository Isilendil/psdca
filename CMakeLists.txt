cmake_minimum_required(VERSION 3.3)
project(psdca)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -O0")

set(SOURCE_FILES
        linear_accl.cc
        linear_classifier.cc
        linear_classifier.hh
        linear_dual.cc
        linear_fista.cc
        linear_trainer.cc
        linear_trainer.hh
)

set(train_main train.cc)
add_executable(train ${SOURCE_FILES} ${train_main})
target_link_libraries(train m)

set(predict_main predict.cc)
add_executable(predict ${SOURCE_FILES} ${predict_main})
target_link_libraries(predict m)
