add_executable(worker-lambda worker_lambda.cpp)

target_link_libraries(worker-lambda
        aws
        AWS::aws-lambda-runtime
        worker_lib
        )

if(FAASM_AWS_SUPPORT)
aws_lambda_package_target(worker-lambda)
endif()