# HEADERS

set(LIBRARY_HEADERS
        mnist_loader/mnist_reader.hpp
        mnist_loader/mnist_reader_common.hpp
        mnist_loader/mnist_reader_less.hpp
        mnist_loader/mnist_utils.hpp
        )

set(LIBRARY_INCLUDES
        ./
        )

add_library(${PROJECT_NAME} STATIC ${LIBRARY_HEADERS})
target_include_directories(${PROJECT_NAME} PUBLIC ${LIBRARY_INCLUDES})
target_compile_definitions(${PROJECT_NAME} INTERFACE MNIST_DATA_LOCATION="${MNIST_DATA_DIR}")

set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)
add_library(mmpaszkowski::${PROJECT_NAME} ALIAS ${PROJECT_NAME})
