# image-processing


矢量图转换：

（1）检查图片不是位图的话，使用ImageMagick先把图转换成bmp位图，参考：https://github.com/ImageMagick/ImageMagick

（2）使用potrace把位图转换成矢量图，参考：https://github.com/skyrpex/potrace

图片放大：
 a、使用sd进行图片高清放大，其中一种方法参考：
	自行部署sd模型服务
	url:/extra_images
	参数参考： 
		$imageData = file_get_contents($imagePath);
				// 将图片内容转换为 base64 编码
				$base64Image = base64_encode($imageData);
				$param = [
					"resize_mode"=> 0,
					"show_extras_results"=> true,
					"gfpgan_visibility"=> 0,
					"codeformer_visibility"=> 0,
					"codeformer_weight"=> 0,
					"upscaling_resize"=> 4,
					"upscaling_crop"=> true,
					"upscaler_1"=> "Lanczos",
					"upscaler_2"=> "None",
					"extras_upscaler_2_visibility"=> 0,
					"upscale_first"=> false,
					"image" => $base64Image
				];
  b、纯前端的upscaler参考：https://github.com/gosunny2050/UpscalerJS
(3) 移除背景，方法参考： 
    https://github.com/gosunny2050/backgroundremover
